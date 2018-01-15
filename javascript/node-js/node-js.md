# NodeJS

* nodejs can handle more than 1M concurrent connections in a 16GB server [study](http://blog.caustik.com/2012/08/19/node-js-w1m-concurrent-connections/) and over 600k websocket connections.

## Best Practices

### Graceful shutdown for your applications

When you deploy a new version of your application, the old must be replaced. The process manager you are using (no matter if it is Heroku, Kubernetes, supervisor or anything else) will first send a **SIGTERM** signal to the application to let it know, that it is going to be killed. 

Once it gets this signal, it should:

* stop accepting new requests
* finish all the ongoing requests
* and clean up database connections or file locks.

[terminus](https://github.com/godaddy/terminus) is an npm package to help gracefully shutdown nodeJS apps.


## Standards

http://node-machine.org/

## Website indicators

- [ES6 speed on differente node engines](http://kpdecker.github.io/six-speed/) 

## Compression

```javascript
    /**
     * GZip helper
     * To use this, the build has to compress the bundles into gzip.
     * @return {undefined}
     */
    sendGzip (req, res) {

        let filePath = path.resolve(`public/${req.path}`);

        if (/css/.test(filePath)) {
            res.setHeader('Content-Type', 'text/css');
        }

        if (!fs.existsSync(filePath)) {
            res.setHeader('Content-Encoding', 'gzip');
            filePath += '.gz';
        }

        res.sendFile(filePath);
    }

// or use `npm compression`
import compress from 'compression';
app.use(compress());
```

- vim: associate `.hbs` file extension with HTML by adding the line `au BufNewFile, BufRead *.hbs set file type=html` to your *.vimrc* file


## Page tests

- run zombie tests with `mocha -u tdd -R spec qa/tests-cross.js 2>/dev/null`
- `/dev/null` hides stack trace
- [linkChecker](http://wummel.github.io/linkchecker`

## HTTP

- HTTP ports use 1023+ (pg 54)
- HTTP queryStrings must be URL encoded (eg. using `encodeURIComponent`
- URL hash (fragment) # is only in the browser (eg. `id='chapter-03')

## Tools

- [ink](https://github.com/vadimdemedes/ink) CLI tools with React
- [zeit pkg](https://github.com/zeit/pkg) - binary nodejs apps