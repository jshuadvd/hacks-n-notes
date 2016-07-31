# Middleware
> Middleware is a function that takes `req`, `res`, `next` params to encapsulate HTTP functionality

- to insert middleware use `app.use`

## Common Middleware

- body-parser
- connect.compress (gzip)
- cookie parser
- cookie-session
- express-session

### csurf
- `app.use(require(csurf());`
- protects against cross-site request forgery (CSRF)) attacks
- must be linked after `express-session`

### directory
- `app.use(connect.directory())`
- provides directory listing for static files

### errorhandler
- `app.use(require(errorhandler)())`
- provides stack traces & error messages to the client.
- Do not use in production.

### static-favicon
- serves favicon

### morgan
- automated logging from all requests

### method-override
- provides support for `x-http-method-override` request header to allow browsers to fake using HTTP methods other than GET & POST. Useful for debugging. Only needed if writting APIs.

### query
- parses `querystring``
- Already comes in express

### response-time
- Adds `X-Response-Time` header to the response (milliseconds)
- Useful for performance tunning

### static
- Provides support to serve static files
- You can use it multiple times to specify multiple directories

### vhost
- virtual hosts




















