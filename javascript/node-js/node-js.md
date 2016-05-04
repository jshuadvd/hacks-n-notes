# NodeJS


## Compression

```javascript
    /**
     * GZip helper
     *
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
```
