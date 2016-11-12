# Networks
> Send bits through electricity, light or radio.

## Bit transfer

- 1 bit is a boolean
- 1 byte = 8 bits
- 8 million bits = 1 MB

- To transfer `1` you send one electric pulse. 
- To transfer `0` you omit the electric pulse and this has to be in a time frame. eg. bit per second


### Bandwidth
> Transmission capacity, measured by bitrate

- **Bitrate:** the number of bits per second a system can transmit
- **Latency:** time it takes for a bit to travel from sender to receiver

### Transfer medium

- Electricity through copper wires eg. Ethernet, is cheap but has a lot of signal loss.
- Light is faster, minimal signal loss, can be transferred by fiber.

## DNS (Domain Name Server)

### Domain name mapping

- `A` record maps a domain name directly to an IP address (preferred)
- `CNAME` record maps one domain name to another and are less flexible.

- domain mapping is usually aggressively cached (can take up to 48 hours to update)
- if you want to show the change immediately, redirect the current server to the Coming soon while you wait for the DNS to update the cache.


