TLS Essential Security

Justin Mayer  
@jmayer  
monitorial.com  
works in Pelican python

how to check on runtime if the js has been tampered?

[https://portier.github.io](https://portier.github.io)

auth method:  
 DNS-01, webroot, standard, manual, apache/nginx

Certbot - github. lets encrypt

[https://caddyserver.com](https://caddyserver.com) - tool to deploy certs

http2 makes TLS fingerprinting more difficult

HSTS \(http transport sec\)

www.hstspreload.org

x-frame-options sameorigin  
x-content-type-options nosniff

OCSP stapling - [https://en.wikipedia.org/wiki/OCSP\_stapling](https://en.wikipedia.org/wiki/OCSP_stapling)

CSP  - [https://en.wikipedia.org/wiki/Content\_Security\_Policy](https://en.wikipedia.org/wiki/Content_Security_Policy)  
[https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)  
whitelist scripts, css, images, fonts, etc.  
no inline scripts or css  
block anything else  
doesn’t work with TypeKit because it dynamically injects scripts  
[https://cspvalidator.org/\#url=https://cspvalidator.org/](https://cspvalidator.org/#url=https://cspvalidator.org/)  
don’t run script you can’t control

AMP [https://www.ampproject.org/](https://www.ampproject.org/)  \(not good\)

[https://www.srihash.org/](https://www.srihash.org/)

HPKP \(don’t work very well with letsencrypt\)

certs should support SCT \(timestamps\)

\(coming soon\)  
TLS 1.3  
CAA records - to whitelist which Cert Auth can issue certs for your domain

[https://twitter.com/techsolidarity](https://twitter.com/techsolidarity)

[https://github.com/trailofbits/algo](https://github.com/trailofbits/algo) - Algo VPN. doesn’t need client software installed. supports macOS/linux

DNSCrypt  
brew install dnscrypt-proxy —with-plugins  
sudo brew services start dnscrypt-proxy \# change dns resolver to 127.0.0.1  
test with [https://dnsleaktest.com/](https://dnsleaktest.com/)

[https://justinmayer.com/](https://justinmayer.com/)

## Chris Roberts

@sidragon1

[http://www.acalvio.com](http://www.acalvio.com)

* don't do BYOD 
* pen testing is often only running tools: Penwave or Trackwave 
* pentest before releasing
* assume that the bad guys are in your network 
* resumes, whitepapers, etc can be payload payloaded 
* humans will always make a mistake 
* nanotechnology hacked 
* IoT hacked 
* nano machines 
* [http://www.cellocad.org](http://www.cellocad.org)
* user behavior analytics 
* add AI in security tools 
* [https://packetstormsecurity.com](https://packetstormsecurity.com)
* deception as defense 

## Gary Mcgraw

cigital bought by synopsis

BSIMM

[https://www.bsimm.com](https://www.bsimm.com/)

Gary book

[https://www.garymcgraw.com/technology/books/](https://www.garymcgraw.com/technology/books/)

use static analysis tool for code review

pen testing. need typed language to do proper static analysis

security testers need to know how to understand the code that they have to test

architecture risk analysis. check where two architects disagree about the spec interpretation and there might be a bug there. it is unscalable because you need a superman to do it.

[https://www.computer.org/cms/CYBSI/docs/Top-10-Flaws.pdf](https://www.computer.org/cms/CYBSI/docs/Top-10-Flaws.pdf)

analysis your open source dependencies

pen testing is becoming a commodity

it's better to do pen testing before deploying to prod

have at least two pen testing outsourcing teams so you hear two opinions in case one of them aren't telling you the whole thing. put honey pots.

[https://www.cigital.com/podcast/](https://www.cigital.com/podcast/)

[sweet.com](http://sweet.com/)

[gem@cigital.com](mailto:gem@cigital.com)

@cigitalgem

when finding an issue report it and offer a solution and help

## Brent Johnson

@ndm Neil

localstorage with csp can be more effective against csurf than cookies

functions that generate html risk xss

build apps with security in mind since the beginning

research http headers

separate code and data

watch out for cdn vulnerabilities

[https://medium.com/starting-up-security/starting-up-security-87839ab21bae\#.fqs0cvjn9](https://medium.com/starting-up-security/starting-up-security-87839ab21bae#.fqs0cvjn9)

[http://cto-security-checklist.sqreen.io](http://cto-security-checklist.sqreen.io/)



## bad bots

Tin Zaw

from verizon

[owasp.org](http://owasp.org/)

OAT - owasp automated threats

OWASP 20

there is a handbook

[https://www.owasp.org/index.php/OWASP\_Automated\_Threats\_to\_Web\_Applications](https://www.owasp.org/index.php/OWASP_Automated_Threats_to_Web_Applications)

credential cracking

credential stuffing

rate limit with ip address and fingerprint

have elastic capacity

#### credit card abuse

carding - stolen cc validation

cardcracking

cashing out

scalping - bots buy faster than humans like Nike shoes or comic con tickets

sniping - to get the best bids

counter measures





