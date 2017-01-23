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

## HTTP Security

- trust no HTTP request even if it is https
- https://addons.mozilla.org/en-US/firefox/addon/tamper-data/
- when you have only one party sign the hash of the cookie. (single key digital signature), [HMAC](https://en.wikipedia.org/wiki/Hash-based_message_authentication_code). if you have multiple parties then sign with asymetric.


### HTTP Request Headers
- the Referer is the website where the req comes from
- don't trust user-agent


