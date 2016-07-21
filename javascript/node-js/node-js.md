# NodeJS


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