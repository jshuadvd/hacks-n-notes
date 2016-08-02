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

### Scale

- **Scale-out** is more cost efficient than **scale-in**
- Persist with filesystems only read-only data like logging and backups

#### Scale-out with App Clusters

- single-server form of scaling out
- create on independent server for each core (CPU)
- don't create more than one cluster per core otherwise the extra servers will be useless

##### The Pros

- Maximize server performance (hardware or virtual machine)
- low overhead to test your app under parallel conditions

