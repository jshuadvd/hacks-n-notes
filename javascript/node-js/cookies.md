# Cookies

## Externalizing Credentials

### Cookie secret

> **Cookie secret** makes cookies secure.

- it's a string that's known to the server and used to encrypt secure cookies before they're sent to the client.
- it can be a random string eg. [Password generator tool](http://preshing.com/20110811/xkcd-password-generator/)

### Parse cookies

- npm module [cookie-parser](https://www.npmjs.com/package/cookie-parser) is a middleware to handle cookies.
- `app.use(require('cookie-parser')(credentials.cookieSecret));`
- 

