# REST APIs

## CORS 
> (Cross-Origin Resource Sharing)

The protocol, domain and port must match.

### Disable CORS
> CORS allows you to lift this restriction on a case-by-case basis

- even allowing you to list which domains specifically are allowed to access the script
- CORS is implemented through the `Access-Control-Allow-Origin` header
- npm package **cors**
- - `app.use(require('cors')())`
- to implemente CORS only on a route
- - `app.use('/api', require('cors')())`

## Test APIs

Use npm package **restler** to do the XHR requests 
- github.com/danwrong/restler











