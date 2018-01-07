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

## Examples

> Amazing REST APIs for Inspiration

* [DigitalOcean API](https://developers.digitalocean.com/documentation/v2/#introduction)
* [GitHub API](https://developer.github.com/v3/)
* [Stripe API](https://stripe.com/docs/api)
* [Twilio API](https://www.twilio.com/docs/api/rest)


## HTTP Headers

* [list of HTTP headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)
* use HTTP headers to send metadata like pagination, rate limiting, or authentication.
* Node.js imposes an 80KB size limit on the headers object to prevent DoS attacks. Therefor avoid the total size of the HTTP headers (including the status line) to exceed `HTTP_MAX_HEADER_SIZE`.

## Rate Limiting

> Rate limiting is used to control how many requests a given consumer can send to the API.

To tell your API users how many requests they have left, set the following headers:

* `X-Rate-Limit-Limit`, the number of requests allowed in a given time interval
* `X-Rate-Limit-Remaining`, the number of requests remaining in the same interval,
* `X-Rate-Limit-Reset`, the time when the rate limit will be reset.


## Test APIs

Use npm package **restler** to do the XHR requests 
- github.com/danwrong/restler
- [supertest](https://github.com/visionmedia/supertest)












