# NodeJS Express

- creator [TJ Holowaychuk](https://medium.com/@tjholowaychuk)
- don't need `app.use(app.router)` after express v3

## NPM Licenses

- npm [license-checker](https://github.com/davglass/license-checker) checks licenses of npm package dependencies.
- some npm packages might not allow the use on closed-source software.
- **MIT** license allows you to do anything
- **GNU/GPL** license can NOT be used in close-sourced software
- Dual license MIT+GPL is possible.

## Cookies

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