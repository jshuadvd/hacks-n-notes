# NodeJS Express

- creator [TJ Holowaychuk](https://medium.com/@tjholowaychuk)
- don't need `app.use(app.router)` after express v3

## NPM Licenses

- npm [license-checker](https://github.com/davglass/license-checker) checks licenses of npm package dependencies.
- some npm packages might not allow the use on closed-source software.
- **MIT** license allows you to do anything
- **GNU/GPL** license can NOT be used in close-sourced software
- Dual license MIT+GPL is possible.



## Browser parsing

```javascript
    import UAParser from 'ua-parser';
    
    browserCheck (req, res, next) {

        const browser = UAParser.parse(req.headers['user-agent']);

        let isBrowserSupported = false,
            isMobile = false;

        SupportedBrowsers.forEach((f) => {
            if (/Mobile/.test(browser.ua.family
                || /Android/.test(browser.os.family))) {
                isMobile = true;
            }
            if (browser.ua.family === f.family && browser.ua.major >= f.major) {
                isBrowserSupported = true;
            }
        }); 

        if (!isBrowserSupported) {
          // complain about the browser
        } 
    }
```

## Request Headers

> info sent by the browser to the server

- url
- language
- user agent (browser, OS, hardware)

## Response Headers

> server also sends invisible info

- Content-Type
- is it compressed?
- encoding type
- cache expiration
- server type and OS (hint for hackers... `app.disable('x-powered-by')`

## Content Type
- it is an Internet Media Type
- MIME was a precursor type/subtype; params eg. `text/html; charset=UTF-8`
- [Internet Media Types](www.iana.org/assignments/media-types/media-types.xhtml)

## Request Body

- most common media type for POST bodies is `application/x-www-form-urlencoded` which is similar to querystring
- if POST needs file uploads it uses `multipart/form-data`
- AJAX uses `application/json`
- Normal GET requests lack bodies

## Parameters

Can come from

- querystring
- session
- request body
- named routing parameters

## Request Object

> Created as an instance of `http.IncomingMessage`

- `req.params`: [by express] array with named route parameters
- `req.param()`: [by express] method to get the named route parameter
- `req.query`: [by express] dictionary of querystring parameters
- `req.body`: [by express] Object dictionary containing POST params from body. To make it available you need middleware
- `req.route`: [by express] info about route. Useful for debugging
- `req.cookies` & `req.signedCookies`: [by express] cookie dictionary
- `req.headers`: [Node] headers from client
- `req.accepts`: [express] method to determine if a client accepts certain types. eg. MIME types, arrays, comma list
- `req.ip`: [express] client ip address
- `req.path`: [express] path without protocol, host, port or querystring
- `req.host`: [express] method that returns hostname from client. This can be spoofed. Warning: should not be used for security purposes.
- `req.xhr`: [express] boolean states if request was AJAX
- `req.protocol`: [express] http or https
- `req.secure`: [express] boolean equivalent to `req.protocol === 'https'`
- `req.url` / `req.originalUrl`: [node/ express]
- `req.acceptedLanguages`: [express] array of human languages the client prefer. Parsed from `req.header`

## Response Object

> created on `http.ServerResponse`

- `res.status()`: method to set status code (HTTP). Default is 200. FOr redirects use 301, 302, 303 & 307 (use `res.redirect` method instead)
- `res.set(name, value)`: set response header
- `res.cookie(name, value, [options])` & `res.clearCookie(name, [options])`: sets or clears cookies that will be stared on the client.
- `res.redirect([status], url)`: Redirects browser. Default code 302 (found). Avoid redirection unless permanently moving a page. 301 (Moved Permanently).
- `res.send(body)` & `res.send(status.body)`: Sends response to client. Defaults content type `text/html`. To change `res.set('Content-Type', 'text/plain'). If body is object or array it sends it as json
- `res.json(json)`: sends JSON. Use this instead of `res.send` if sending JSON.
- `res.jsonp(json)`: sends JSONP
- `res.type(type)`: Method equivalent to `res.set('Content-Type', type)` except it will attempt to map file extensions to an Internet media type eg. `res.type('txt')` to `text/plain`
- `res.format(object)`: Method to send different content depending on the Accept request header.
```js
app.get('/api/tours', (req, res) => {
  var toursXml = '<?xml version="1.0"?><tour>Tour1</tour>';
  var toursText = 'Tour1';
  res.format({
    'application/json': () => res.json(tours),
    'application/xml': () => {
      res.type('application/xml');
      res.send(toursXml);
    },
    'text/xml': () => {
      res.type('text/xml');
      res.send(toursXml);
    },
    'text/plain': () => {
      res.type('text/plain');
      res.send(toursText);
    }
});
```
- `res.attachment([filename])` & `res.download(path, [filename], [callback])`: Both of these methods set a response header called Content-Disposition to **attachment**. This will prompt the browser to download the content instead of displaying it in a browser. **attachment** will only set the headers but you'll have to send the conent. With **download** you can specify a file path to send.
- `res.sendFile(path, [options], [callback])`: will read the contents of a file and send the contents.
- `res.links(links)`: sets links response header.
- `res.locals` & `res.render(view, [locals], callback)`: `res.locals` is an object with default context for rendering views. `res.render` will render a view using the configured templating engine.

## Form Handling

- Use redirect 303 instead of direct HTML response since it doesn't interfere with back button & book marking
- Use body-parser middleware for POST body
- You can use `querystring` on POST by adding it to the forms action path eg. `<form action="/process?form=news">`
- Use the same URL endpoint for AJAX and normal POST fallback. This hides implementation details. **good**: `/offers` **bad** `/api/offers`
- Detect AJAX. `if(req.xhr || req.accepts('json, html') === 'json') {`

## File Uploads

Two famous libraries for multipart processing:
- Busboy
- Formidable (easier to uses)

eg.
```html
<form enctype="multipart/formm-data" action="/" method="POST">
  <input type="file" accept="image/*" name="photo" />
```

and in the server

```js
var formidable = require('formidable');

app.get('/contest/vacation-photo', function(req, res) {
  var now = new Date();
  res.render('contest/vacation-photo', {
    year: now.getFullYear(), month: now.getMonth()
  });
});

app.post('/contest/vacation-photo/:year/:month', function(req, res) {
  var form = new formidable.IncomingForm();
  form.parse(req, function(err, fields, files) {
    if(err) return res.redirect(303, '/error');
    console.log('received fields:');
    console.log(fields);
    console.log('received files');
    console.log(files);
    res.redirect(303, '/thank-you');
  });
});
```

## Cookies & Sessions

HTTP is stateless.
- Every request is independent of the previous ones
- Cookies & sessions save state

Cookies are visible to users

**Signed Cookies** can obfuscate its contents but not encrypt

Don't trust cookies
- Use **signed cookies** to ensure they're not tampered
- cookies can be used for XSS attacks

Prefer session over cookies
- Sessions use cookies but they are safer
- Express knows how to handle sessions







## Stress Testing

> to have confidence that your app will function under the load of hundreds of thousands of simultaneous requests

- node modele [loadtest](https://www.npmjs.com/package/loadtest)

```js
var loadtest = require('loadtest');
var expect = require('chai').expect;

suite('Stress tests', function () {
  test('Homepage should handle 100 requests in a second', function (done) {
    var options = {
      url: 'http://localhost:3000',
      concurrency: 4,
      maxRequests: 100
    };
  
    loadtest.loadTest(options, function(err, result) {
      expect(!err);
      expect(result.totalTimeSeconds < 1);
      done();
    });
  });
});
```





















