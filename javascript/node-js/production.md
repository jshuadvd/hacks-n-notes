# Production

## Logging
- morgan for dev

### [express-logger](https://www.npmjs.com/package/express-logger) 
> for prod

- supports log rotation (every 24 hours the log is copied and a new one starts)

```js
switch(app.get('env')){
  case 'development':
    // compact, colorful dev logging
    app.use(require('morgan')('dev'));
    break;
  case 'production':
    // module 'express-logger' supports daily log rotation
    app.use(require('express-logger')({
      path: __dirname + '/log/requests.log'
    }));
    break;
}
```

## Scale

- **Scale-out** is more cost efficient than **scale-up**
- Persist with filesystems only read-only data like logging and backups

### Scale-out with App Clusters

- single-server form of scaling out
- create on independent server for each core (CPU)
- don't create more than one cluster per core otherwise the extra servers will be useless

#### The Pros

- Maximize server performance (hardware or virtual machine)
- low overhead to test your app under parallel conditions

```js
// Web development with Node & Express pg. 134
var cluster = require('cluster');

function startWorker() {
  var worker = cluster.fork();
  console.log('CLUSTER: Worker %d started', worker.id);
}

if (cluster.isMaster) {
  require('os').cpus().forEach(() => {
    startWorker();
  });

  // log any workers that disconnect; if a worker disconnects, it
  // should then exit so we'll wait for the exit event to spawn
  // a new worker to replace it
  cluster.on('disconnect', (worker) => {
    console.log('CLUSTER: WOrker % disconnected from the cluster.', worker.id);
  });

  // when a worker dies (exits), create a worker to replace it
  cluster.on('exit', (worker, code, signal) {
    console.log('CLUSTER: Worker %d died with exit code %d (%s)', worker.id, code, signal);
    startWorker();
  });
} else {
    // start our app on worker;
    require('./meadowlark.js')();
}

```
- when a script is run directly, `require.main === module` will be true.
- if false, it means your script has been loaded from another script using require.
- [cluster](https://www.npmjs.com/package/cluster)
- virtual machines default to a single core.

### Scaling Out with Multiple Servers

- To scale out you need a proxy server (often called a reverse proxy or forward-facing proxy.)
- Most popular: Nginx and HAProxy
- Dev proxies: [proxy](https://www.npmjs.com/package/proxy) and [node-http-proxy](https://www.npmjs.com/package/node-http-proxy)

#### Working with proxies
- if you use a proxy server, make sure to tell Express to trust it with `app.enable('trust proxy');`
- this will ensure that `req.ip`, `req.protocol`, and `req.secure` reflect details about the connection client <> proxy, and not client<>server
- `req.ips` will be an array of ips with original client and the names or IP addresses of intermediate proxies

## Handling Uncaught Exceptions

- When Express executes route handlers, it wraps them in a try/catch block, so it isn't an uncaught exception.
- Express will log the exception on the server side, and the client will get an ugly stack dump
- The server will still be stable, and other requests will continue to be served correctly.
- Add error handler after all your routes


```js
// This is the only exceptions that Express can catch
app.get('/fail', (req, res) => {
  throw new Error('Nope:');
});

app.use((err, req, res, next) => {
  console.error(err.stack);
  app.status(500).render('500');
});

// This won't be catched by Express
app.get('/epic-fail', (req, res) => {
  process.nextTick(() => {
    throw new Error('Kaboom!');
  });
});
```

- `process.nextTick(function)` & `setTimeout(function, 0)` execute when Node is idle, asynchronously. This causes Node to lose context about the http request it was served from so it shuts down the server, because it's in an undefined state.
- Node can't know the purpose of the function, or its caller. So it can no longer assume that any further functions will work correctly.
- When an uncaught exception occurs the best thing is to stop the server and have a failover mechanism.
- An easy failover mechanism can be a cluster.

### Two mechanisms to restart servers after unacaught exceptions

> **Domains** and **uncaughtExceptions events** 

#### Domains

- The most recent and recommended approach (2014)
- Domains wrap the uncaught exceptions in a known context. This allows to gracefully shutdown the server

```js
app.use((req, res, next) => {
  // create a domain for this request
  var domain = require('domain').create();
  // handle errors on this domain
  domain.on('error', (err) => {
    console.error('DOMAIN ERROR CAUGHT\n', err.stack);
    try {
      // failsafe shutdown in 5 seconds
      setTimeout(() => {
        console.error('Failsafe shutdown.');
        process.exit(1);
      }, 5000);

      // disconnect from the cluster
      var worker = require('cluster').worker;
      if (worker) worker.disconnect();

      // stop taking new requests
      server.close();

      try {
        // attempt to use Express error route
        next(err);
      } catch (err) {
        // if Express error route failed, try
        // plain Node response
        console.error('Express error mechanism failed.\n', err.stack);
        res.statusCode = 500;
        res.setHeader('content-type', 'text/plain');
        res.end('Server error');
      }
    } catch(err) {
      console.error('Unable to send 500 response.\n', err.stack);
    }
  });

  // add the request and reponse objectes to the domain
  domain.add(req);
  domain.add(res);

  // execute the rest of the request chain in the domain
   domain.run(next);
});

// other middleware and routes go here
var server = http.createServer(app).listen(app.get('port'), () => {
  console.log('Listening on port %d.', app.get('port'));
});
```

- domains are set pu as a middleware

##### Articles
- [William Bert's article: The 4 Keys to 100% Uptime with NodeJS](http://engineering.curiositymedia.com/blog/2013/12/20/the-4-keys-to-100-uptime-with-nodejs)
- [NodJS Domain documentation](https://nodejs.org/api/domain.html)
 
#### uncaughtExceptions events
-  is going to be deprecated


## Monitoring your app

- use third-party monitoring services additionally to your server monitoring
- if your server goes down it might not have time to send an SOS. 3rd party monitoring would help diversify the monitoring

### Services (Uptime monitors)

#### [UptimeRobot](https://uptimerobot.com/)
- alerts can go to email, SMS, Twitter, iPhone app
- can monitor the return code from a single page (HTTP codes)

#### [Pingdom](https://www.pingdom.com/)
#### [Site 24x7](http://www.site24x7.com/)

### Application Failures
- Monitor keywords suc as "server failure"
- handle gracefully with a "We're sorry" message and ping the staff for help
- A sophisticated approach could be AWS Simple Notification Service (SNS)

#### [GetSentry](www.getsentry.com)
#### [Airbrake](http://airbrake.io)















