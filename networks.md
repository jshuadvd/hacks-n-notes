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
- Light is faster, minimal signal loss, can be transferred by fiber-optic cable.
- Radio waves are used for wireless transmission

## IP (InternetWorking Protocol)
> The Internet is the Network of Networks. It is a design philosophy and architecture expressed in a set of protocols

- Invented by [Vint Cerf](https://en.wikipedia.org/wiki/Vint_Cerf) & [Bob Kahn](https://en.wikipedia.org/wiki/Bob_Kahn)

- A **Protocol** is a well-known set of rules and standards used to communicate between machines.
- All devices in the internet have unique addresses

### IP Address

#### IPv4
> Provides for 4Billion unique addresses

- IPv4 has 4 parts consisting of 8 bits each ~ 0 to 255 in decimals.
- The first part represents the country/network
- The second part is the region/network
- The third is the subnetwork
- The fourth is the device

#### IPv6

- 128 bits per address composed of 8 parts
- provides 340 undecillion unique addresses


## DNS (Domain Name System)

### Domain name mapping
> Connected through a domain name hierarchy


- `A` record maps a domain name directly to an IP address (preferred)
- `CNAME` record maps one domain name to another and are less flexible.

- domain mapping is usually aggressively cached (can take up to 48 hours to update)
- if you want to show the change immediately, redirect the current server to the Coming soon while you wait for the DNS to update the cache.


### DNS Spoofing
- When a hacker breaks into a DNS Server and changes a domain name cache to point to a different IP address.

## Packets and routers

- Data is chunked into packets and each of these travel in different routes from sender to receiver.
- The packets my arrive to the receiver at different times but the receiver will wait untill all is ready to assemble.
- each packet contains it's IP address of where it came from and where it's going
- if one of the network routes is congested, the router might send the packets in different routes and in different order
- Routers are computers dedicated to forward packets to their destination and balance the network traffic
- The diversification of routes makes the internet reliable and difficult to take down

### TCP (Transmission Control Protocol)
> Manages all your sending and receiving your data as packets

- TCP makes sure all packets arrived and send a confirmation status to the sender.
- If there are any packets missing, TCP will request the sender to re-send those packets.