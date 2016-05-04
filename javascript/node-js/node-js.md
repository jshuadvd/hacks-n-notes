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
