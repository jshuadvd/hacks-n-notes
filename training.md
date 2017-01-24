# Secure coding education
- Jim Manico
- @manicode
- jim@manico.net
- www.manicode.com

- [ ] make a process checklist for security

- VPC is not enough to protect microservices.
- WAF (Web App Firewall)
- don't hack without legal written permission.
- being compliant doesn't equal being secure.
- Step-skipping-attack
- IE6 is super insecure, secure softwaree can't be built for this browser
- security salmon
- [ASVS](https://www.owasp.org/index.php/Category:OWASP_Application_Security_Verification_Standard_Project) - Application Security Verification Standard
- [NIST](http://csrc.nist.gov/) National Institute of Standards and Technology

## HTTP Security

- trust no HTTP request even if it is https
- https://addons.mozilla.org/en-US/firefox/addon/tamper-data/
- when you have only one party sign the hash of the cookie. (single key digital signature), [HMAC](https://en.wikipedia.org/wiki/Hash-based_message_authentication_code). if you have multiple parties then sign with asymetric.
- always use https

### HTTP Request Headers

- the Referrer is the website where the req comes from. This can leak GET querystring. Even in https, it can be cached, bookemarked, etc
- <form> uses method="GET" by default
- never put sensitive data on the URI (querystring)
- don't trust user-agent
- detect and block certain browsers: validate and whitelist user agents and browsers versions.. notify if any case like that happens and notify the security team, specially in intranet. Prevent webscrapping, malware, and hacking. block webTV since doesn't support https
- use html rel="noreferrer"
- use redirect interstitial popup to clean referer and other data
- count-block the failed login attempts to prevent bruteforce. Track per userName, not cookie or other thing.

### HTTP Response Headers

- don't leak the server information eg. `powered by Express v4`. Also don't post it on the job descriptions. or lie about the powered by to catch hackers. Hackers can figure out the server type through server-fingerprinting.
- use honeytoken inputs and hidden params to detect hackers

#### Cookies

- httpOnly
- enable `secure` flag
- make them expirable
- activate `SameSite` to avoid cookie leaving the browser unless the current page origin matches the target
- avoid persistent cookies

#### X-Frame-Options 
- protects from clickjacking


## Clickjacking / UI Redress
- gmail example

## SQL injection
- block any http request that looks like SQL injection
- `or` attack. `'1'='1'`
- usually the first user in the user_table is the root user
- timing attack
- [SQL Map](http://sqlmap.org/)
- anytime a sql statement is build by concat strings, it has risk
- even valid data can cause injection eg `'--@manico.net`
- you can't parametrize column name and tablename in some languages. you have to validate those names.

## Auth
- every single webpage by default should be treated as auth-required page instead of only validating the pages that should be logged in.
- do re-authentication eg in Amazon when the user is going to checkout the shopping cart
- re-authentication to prevent session hijacking and CSRF: cross-site scripting attacks, 
- re-auth before being able to reset password or email.. since email is used to change password
- SMS for MFA is easy to get around
- login/pwd is not enough
- [TOTP](https://en.wikipedia.org/wiki/Time-based_One-time_Password_Algorithm) - easily phishable
- [FIDO standard](https://fidoalliance.org) - the safest since it checks to the hardware. eg. Yubikey
- push notifications to auth
- The german banks have very effective security policies.
- absolute timeout vs idle timeout
- in login/pwd auth failure don't specify what failed 
- send all usernames over HTTPS
- time attacks to see which usernames are good or bad
- [Bcrypt](https://en.wikipedia.org/wiki/Bcrypt) - to hash passwords
- don't use usernames as public like twitter do. Use your login username and have another that's the display name
- if you lock out an account for brute-forcing, don't notify them on the website, but send them an email.
- do phishing campaign to your own company to detect any weaknesses and to educate.
- for single-sign on use OpenId-Connect
- use mutual TLS from server to server



### Session Fixation
- create new sesion ID at login to protect 

### Password storing

#### Best practices
- don't limit the chars or lenght of passwords


#### Avoid
- hashing is easy decifered with the proper equipment. hashkiller.co.uk , arteschnica.com 6billion passwords per second
- encryption - superadmins can decrypt passwords.. so that's the weakness
- salted hash - they will throw an assault of trillion times to the superadmin

#### Encryption
- [PBKDF2](https://en.wikipedia.org/wiki/PBKDF2)
- [scrypt](https://en.wikipedia.org/wiki/Scrypt)
- salt is meant to prevent dedupe attacks, not brute force attacks
- a *work factor* how much work has to be applied to decrypt, that translates into time.
- [RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem))


### OAuth

- delegation framework
- OAuth2.0 is token-based
- it's like a *valet key* - like valet parking key. Has it's limitations for safety reasons. so you don't need to giveout your user/pwd.
- [not out of the box]federation: to give access from one party to another like with a single-sign-on (eg. GE to Salesforce). Federation gives full power, instead of just a subset of features.
- like when an app requests permission to use your twitter account to read your tweets.
- be very careful with tokens. and use them only for delegation.
- refresh_token pattern recommended only for social media. refresh_token is like  Kerberos ticket `https://en.wikipedia.org/wiki/Kerberos_(protocol)`
- tokens can be very dangerous, see [OAuth2 and road to hell](https://hueniverse.com/2012/07/26/oauth-2-0-and-the-road-to-hell/)
- tokens are sent to and from the browser by GET params.

- https://tools.ietf.org/html/rfc6819
- https://tools.ietf.org/html/draft-ietf-oauth-v2-threatmodel-08


#### Oauth2.0 Grant

- the implicit grant is super unsecure

## Angular

- Strict Contextual Escaping - stops XSS

## React
- no CSP support
- bad escaping

