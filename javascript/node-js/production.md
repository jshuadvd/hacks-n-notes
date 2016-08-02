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