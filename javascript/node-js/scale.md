# Scale


- **Scale-out** is more cost efficient than **scale-up**
- Persist with filesystems only read-only data like logging and backups

## Scale-out with App Clusters

- single-server form of scaling out
- create on independent server for each core (CPU)
- don't create more than one cluster per core otherwise the extra servers will be useless

### The Pros

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

## Scaling Out with Multiple Servers

- To scale out you need a proxy server (often called a reverse proxy or forward-facing proxy.)
- Most popular: Nginx and HAProxy
- Dev proxies: [proxy](https://www.npmjs.com/package/proxy) and [node-http-proxy](https://www.npmjs.com/package/node-http-proxy)

### Working with proxies
- if you use a proxy server, make sure to tell Express to trust it with `app.enable('trust proxy');`
- this will ensure that `req.ip`, `req.protocol`, and `req.secure` reflect details about the connection client <> proxy, and not client<>server
- `req.ips` will be an array of ips with original client and the names or IP addresses of intermediate proxies
