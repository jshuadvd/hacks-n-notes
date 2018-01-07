# REST APIs

* [restify](http://restify.com/) is a node framework specialized for REST APIs.

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

## HTTP Headers

* [list of HTTP headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)
* use HTTP headers to send metadata like pagination, rate limiting, or authentication.
* Node.js imposes an 80KB size limit on the headers object to prevent DoS attacks.


## Test APIs

Use npm package **restler** to do the XHR requests 
- github.com/danwrong/restler
- [supertest](https://github.com/visionmedia/supertest)












