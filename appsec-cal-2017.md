TLS Essential Security

Justin Mayer
@jmayer
monitorial.com
works in Pelican python

how to check on runtime if the js has been tampered?

https://portier.github.io

auth method:
 DNS-01, webroot, standard, manual, apache/nginx

Certbot - github. lets encrypt

https://caddyserver.com - tool to deploy certs

http2 makes TLS fingerprinting more difficult
 

HSTS (http transport sec)

www.hstspreload.org

x-frame-options sameorigin
x-content-type-options nosniff

OCSP stapling - https://en.wikipedia.org/wiki/OCSP_stapling

CSP  - https://en.wikipedia.org/wiki/Content_Security_Policy
https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP
whitelist scripts, css, images, fonts, etc.
no inline scripts or css
block anything else
doesn’t work with TypeKit because it dynamically injects scripts
https://cspvalidator.org/#url=https://cspvalidator.org/
don’t run script you can’t control

AMP https://www.ampproject.org/  (not good)

https://www.srihash.org/

HPKP (don’t work very well with letsencrypt)

certs should support SCT (timestamps)

(coming soon)
TLS 1.3 
CAA records - to whitelist which Cert Auth can issue certs for your domain

https://twitter.com/techsolidarity

https://github.com/trailofbits/algo - Algo VPN. doesn’t need client software installed. supports macOS/linux

DNSCrypt 
brew install dnscrypt-proxy —with-plugins
sudo brew services start dnscrypt-proxy # change dns resolver to 127.0.0.1
test with https://dnsleaktest.com/


https://justinmayer.com/