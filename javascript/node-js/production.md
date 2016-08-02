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
```

#### uncaughtExceptions events
-  is going to be deprecated














