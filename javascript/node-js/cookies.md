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

### Set cookies

```js
res.cookie('monster', 'nom nom');
res.cookie('signed_monster', 'nom nom', {signed: true});
```

#### Cookie options

#### domain
- controls the domain and subdomains for the cookie
- Cookie must be assigned to the same domain as its server. Otherwise it won't do nothing.

#### path
- controls the path this cookie applies to

#### maxAge
- expiration time in milliseconds
- this is simpler than `expires`

#### secure
- if true will send cookie only over a secure HTTPS connection



### Retrieve cookies from client

```js
var monster = req.cookies.monster;
var signedMonster = req.signedCookies.monster;
```

### Delete cookie

```js
res.clearCookie('monster');
```










