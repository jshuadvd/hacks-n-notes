# Secure coding education
- Jim Manico
- @manicode
- jim@manico.net
- www.manicode.com

- VPC is not enough to protect microservices.
- WAF (Web App Firewall)
- don't hack without legal written permission.
- being compliant doesn't equal being secure.
- Step-skipping-attack
- IE6 is super insecure, secure softwaree can't be built for this browser

## HTTP Security

- trust no HTTP request even if it is https
- https://addons.mozilla.org/en-US/firefox/addon/tamper-data/
- when you have only one party sign the hash of the cookie. (single key digital signature), [HMAC](https://en.wikipedia.org/wiki/Hash-based_message_authentication_code). if you have multiple parties then sign with asymetric.


### HTTP Request Headers
- the Referrer is the website where the req comes from. This can leak GET querystring. Even in https, it can be cached, bookemarked, etc
- <form> uses method="GET" by default
- never put sensitive data on the URI
- don't trust user-agent
- e validate and whitelist user agents and browsers versions.. notify if any case like that happens and notify the security team, specially in intranet. Prevent webscrapping, malware, and hacking. 


