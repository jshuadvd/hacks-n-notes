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
- enable secure

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
- do re-authentication to prevent session hijacking: cross-site scripting attacks, 
- SMS for MFA is easy to get around
- login/pwd is not enough
- [TOTP](https://en.wikipedia.org/wiki/Time-based_One-time_Password_Algorithm) - easily phishable

## React
- no CSP support
- bad escaping

