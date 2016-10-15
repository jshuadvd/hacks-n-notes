# Cookies
 
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



## Sessions

```javascript
// Set
res.cookie(
  SessionCookie.COOKIE_NAME, 
  sessionId,
  SessionCookie.makeOptions(
    cookieDomain,
    SessionCookie.DEFAULT_MAX_AGE
  )
)
.redirect(nextUrl);

// Get on request
req.cookies.session_id
```

- store state on client
- npm module [cookie-session](https://www.npmjs.com/package/cookie-session)
- helps to handle storing info in the client
- npm module [express-session](https://www.npmjs.com/package/express-session) will store info in the express server (in memory) instead of the client. You can leverage NoSql to sync multi node instances.
- Sessions are useful to save user preferences, auth info, tracking, etc.


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

#### httpOnly
- states that this cookie can only be modified by the server
- this prevents XSS attacks

#### signed
- set to `true` to sign the cookie
- tampered signed cookies will be rejected by the server and will reset the cookies value.

### Retrieve cookies from client

```js
var monster = req.cookies.monster;
var signedMonster = req.signedCookies.monster;
```

### Delete cookie

```js
res.clearCookie('monster');
```










