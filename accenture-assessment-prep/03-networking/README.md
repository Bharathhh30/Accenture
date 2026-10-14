# Networking

## Concepts to learn

- **LAN / WAN:** A LAN covers a limited area such as an office; a WAN connects networks across larger geographic areas.
- **OSI model:** A conceptual seven-layer model: Physical, Data Link, Network, Transport, Session, Presentation, Application. TCP/IP is a practical model with fewer layers.
- **IP and MAC addresses:** IP addresses support logical addressing/routing; MAC addresses identify network interfaces on a local link.
- **Router and switch:** A router forwards packets between IP networks; a Layer-2 switch commonly forwards Ethernet frames within a LAN using MAC addresses. Some Layer-3 switches also route, so use the question's network-layer context.
- **TCP and UDP:** TCP provides ordered, reliable byte-stream delivery; UDP is connectionless with lower overhead and no built-in delivery guarantee.
- **DNS:** Resolves domain names to IP addresses. **DHCP:** Automatically leases network configuration such as IP address and gateway.
- **HTTP / HTTPS:** Web application protocols; HTTPS protects HTTP traffic using TLS.
- **Ports:** Identify application/service endpoints on a host (for example, a web service). IP identifies the host/network interface, not the specific application.
- **Firewall:** Applies traffic rules; it is not the same thing as antivirus or encryption.
- **Bandwidth and latency:** Bandwidth is data-carrying capacity; latency is delay.

## Original practice MCQs

### Questions

1. Which device primarily forwards packets between different IP networks?
   A) Router  B) Switch  C) Keyboard  D) Repeater

2. Which service translates a domain name such as `example.test` into an IP address?
   A) DHCP  B) DNS  C) FTP  D) ARP only

3. Which transport protocol provides reliable, ordered delivery by default?
   A) UDP  B) TCP  C) IP  D) Ethernet

4. Which address is normally used for delivery on a local Ethernet link?
   A) MAC address  B) URL  C) DNS name  D) File path

5. What does DHCP commonly provide to a client?
   A) A source-code compiler  B) Automatic IP configuration  C) File compression  D) Encryption keys only

6. HTTPS primarily adds which protection to web communication?
   A) TLS encryption and server authentication  B) Faster CPU execution  C) Automatic backups  D) DNS registration

7. Which statement best distinguishes bandwidth from latency?
   A) Bandwidth is delay; latency is storage.
   B) Bandwidth is capacity; latency is delay.
   C) They always mean the same thing.
   D) Bandwidth is an IP address.

8. A switch in a typical Ethernet LAN mainly forwards frames based on:
   A) MAC addresses  B) File names  C) Email subjects  D) CPU registers

### Answer key and explanations

1. **A — Router.** Routers move traffic across IP networks.
2. **B — DNS.** DNS performs name resolution.
3. **B — TCP.** TCP includes sequencing, acknowledgments, and retransmission mechanisms.
4. **A — MAC address.** Ethernet uses link-layer addressing for local frame delivery.
5. **B.** DHCP leases settings such as IP address, subnet mask, and gateway.
6. **A.** HTTPS is HTTP carried over TLS; TLS provides confidentiality and integrity and can authenticate the server.
7. **B.** Capacity and delay are different performance measures.
8. **A.** A learning switch builds a MAC address table and forwards frames accordingly.
