# Security
> Security is as strong as the weakest link, and the first link in that chain is the network protocol.

## HTTPS

> HTTP Secure

In the Internet it is possible for third party to intercept packets being transmitted between clients and servers. HTTPS encrypts those packets.

- HTTPS is considered sufficiently secure for banking, corporate security and healthcare
- The server has a *public key certificate* sometimes called SSL certificate.
- `X.509` is a standard format for SSL certificates.

### Certificate authorities
> A certificate authority (CA) makes trusted root certificates available to browser vendors.

- Browser vendors include these trusted root certificates when you install a browser.
- For this chain of trust to work between CA and browsers, your server must use a certificate issued by a CA.
