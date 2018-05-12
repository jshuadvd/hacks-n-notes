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

## Web security

w3c subresource integrity SRI

[http://retirejs.github.io/retire.js/](http://retirejs.github.io/retire.js/)

[https://nodesecurity.io](https://nodesecurity.io/)

CSP

malicious browser extensions

Man-in the browser attack

runtime application self protectionRASP

DOM anti tampering

polymorphic java script

etc/hosts point local to the target and run a downloaded copy of the code

poisonjs de obfuscation

[https://tampermonkey.net](https://tampermonkey.net/)

## ocsp stapling in the wild

Emily stark

Google Chrome

[emilystark.com](http://emilystark.com/)

estark37

devdatta akhawe

Dropbox

[https://en.m.wikipedia.org/wiki/Online\_Certificate\_Status\_Protocol](https://en.m.wikipedia.org/wiki/Online_Certificate_Status_Protocol)

[https://roughtime.googlesource.com/roughtime](https://roughtime.googlesource.com/roughtime)

[https://is.gd/expect\_staple\_spec](https://is.gd/expect_staple_spec)

[https://developers.facebook.com/tools-and-support/](https://developers.facebook.com/tools-and-support/)

## let's encrypt

Jilian karner

https is Auth and encryption

[https://https.cio.gov/](https://https.cio.gov/)

[https://letsencrypt.org](https://letsencrypt.org/)

[https://github.com/letsencrypt](https://github.com/letsencrypt)

HSM hardware security models

root HSM - locked away. princess in the castle.

intermediate HSM - signs all the certs

developers can't deploy to prod

ops can't merge code

shared logs and metrics

[https://developers.google.com/safe-browsing/](https://developers.google.com/safe-browsing/)

[https://certbot.eff.org](https://certbot.eff.org/)

[https://status.io](https://status.io/)





## AppSec pipelines event driven

Matt tesauro

[Matt.teaauro@owasp.org](mailto:Matt.teaauro@owasp.org)

@matt\_tesauro

the Phoenix project book

[https://stackstorm.com](https://stackstorm.com/)

define false positive

automate yourself out of the job in order to scale

build a chat bot to help you answer questions from developers

integrate alerts in slack

expand the devops pipeline with AppSec pipeline

nikto docker

[https://hub.docker.com/r/frapsoft/nikto/](https://hub.docker.com/r/frapsoft/nikto/)

docker swarm

zap docker

[https://blog.mozilla.org/webqa/2016/05/11/docker-owasp-zap-part-one/](https://blog.mozilla.org/webqa/2016/05/11/docker-owasp-zap-part-one/)

chat bots can also tell devs when a code merge fixes a bug in backlog

owasp defect dojo

[https://www.owasp.org/index.php/OWASP\_DefectDojo\_Project](https://www.owasp.org/index.php/OWASP_DefectDojo_Project)

[https://www.appsecpipeline.org](https://www.appsecpipeline.org/)

[https://github.com/mtesauro](https://github.com/mtesauro)

[https://github.com/aaronweaver](https://github.com/aaronweaver)



Apps parringSPA

document APIs

[https://apiblueprint.org](https://apiblueprint.org/)

[manvswebapp.com](http://manvswebapp.com/)

@dan\_kuykendall





