# Offline

> To make web apps work offline use **Cache Manifest**

## Manifest file

- **CACHE MANIFEST** - Files listed under this header will be cached after they are downloaded for the first time.
- **NETWORK** - Files listed under this header require a connection to the server, and will *never* be cached.
- **FALLBACK** - Files listed under this header specifies fallback pages if a page is inaccessible.


### Example

```
CACHE MANIFEST
/theme.css
/logo.gif
/main.js