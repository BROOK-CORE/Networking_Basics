# Networking Notes for Cybersecurity

## 1. What is a Network?
A network is a group of connected devices that communicate and exchange data.

**Example:**  
PC → Switch → Router → Internet

**Cybersecurity:** Networks are where systems, users, and attackers communicate.

---

## 2. IP Address
An IP address identifies a device/interface for communication at the network layer.

**IPv4 example:** `192.168.1.10`  
**IPv6 example:** `2001:db8::1`

**Remember:** IP = network address.

---

## 3. MAC Address
A MAC address identifies a network interface at the data-link layer.

**Example:** `00:1A:2B:3C:4D:5E`

**Remember:** MAC = local network interface address.

---

## 4. IP vs MAC

| IP Address | MAC Address |
|---|---|
| Network-layer address | Data-link-layer address |
| Used for routing | Used for local-link communication |
| Example: `192.168.1.10` | Example: `00:1A:2B:3C:4D:5E` |

---

## 5. Switch
A switch connects devices in a local network and forwards Ethernet frames toward the appropriate port.

**Main idea:**  
Switch → mainly works with MAC addresses.

---

## 6. Router
A router forwards packets between different networks.

**Main idea:**  
Router → mainly works with IP addresses and routing.

---

## 7. Switch vs Router

**Switch:** connects devices within a LAN.  
**Router:** connects/forwards traffic between networks.

---

## 8. Protocol
A protocol is a set of rules used for communication.

**Examples:**
- TCP
- UDP
- IP
- DNS
- DHCP
- HTTP
- HTTPS
- SSH
- ICMP

---

## 9. OSI Model

| Layer | Name | Main Idea |
|---|---|---|
| 7 | Application | Network services used by applications |
| 6 | Presentation | Data representation |
| 5 | Session | Communication sessions |
| 4 | Transport | End-to-end transport |
| 3 | Network | IP and routing |
| 2 | Data Link | Frames, MAC, Ethernet |
| 1 | Physical | Cables, radio, signals |

**Easy memory:**  
Application → Presentation → Session → Transport → Network → Data Link → Physical

---

## 10. TCP
TCP is a connection-oriented transport protocol that provides reliable, ordered delivery.

**Important ideas:**
- Connection-oriented
- Reliable
- Ordered
- Retransmission mechanisms

**Cybersecurity:** TCP connections are common in web, SSH, and many other services.

---

## 11. UDP
UDP is a lightweight, datagram-oriented transport protocol.

**Important ideas:**
- No TCP-style connection establishment
- No delivery guarantee
- Low protocol overhead

**Cybersecurity:** UDP traffic is important in DNS, streaming, VoIP, and many network services.

---

## 12. TCP vs UDP

| TCP | UDP |
|---|---|
| Connection-oriented | Datagram-oriented |
| Reliable delivery mechanisms | No delivery guarantee |
| Ordered stream | No TCP-style ordered stream |
| More protocol overhead | Minimal overhead |

---

## 13. Port
A port identifies a transport-layer communication endpoint associated with a service/application.

**Examples:**
- `22` → SSH
- `53` → DNS
- `80` → HTTP
- `443` → HTTPS

**Example:** `192.168.1.10:443`

**Cybersecurity:** Open ports can reveal reachable services.

---

## 14. Socket
A socket is a communication endpoint.

A simple mental model:

`IP + Port + Transport Protocol`

**Example:**  
`192.168.1.10:443/TCP`

---

## 15. DNS
DNS (Domain Name System) maps domain names to network information, commonly IP addresses.

**Example:**

`example.com → IP address`

**Cybersecurity:** DNS logs can help identify suspicious domains and malware communication.

---

## 16. DHCP
DHCP automatically provides network configuration to clients.

It can provide:
- IP address
- Subnet information
- Default gateway
- DNS configuration

**Basic process:**
`Discover → Offer → Request → Acknowledge`

---

## 17. ARP
ARP is used on IPv4 Ethernet networks to discover the local MAC address associated with an IPv4 address.

**Example:**

`Who has 192.168.1.1?`

`192.168.1.1 → MAC address`

**Cybersecurity:** ARP behavior is important when studying local-network attacks and spoofing.

---

## 18. ICMP
ICMP carries control and error-reporting messages for IP networks.

**Common example:** `ping`

**Cybersecurity:** ICMP traffic can be useful in troubleshooting and network monitoring.

---

## 19. Packet
A packet is a unit of network-layer data.

Different layers use different terms:
- Application → data
- Transport → segment (TCP) / datagram (UDP)
- Network → packet/datagram
- Data Link → frame

---

## 20. Frame
A frame is a data-link-layer unit used to move data across a local link.

Ethernet frames contain information such as:
- Source MAC
- Destination MAC
- Payload

---

## 21. Subnet
A subnet is a logically divided portion of an IP network.

**Example:**

`192.168.1.0/24`

Here:
- Network = `192.168.1.0`
- Prefix = `/24`
- Typical IPv4 host range = `192.168.1.1` to `192.168.1.254`

**Cybersecurity:** Subnetting helps understand network boundaries and segmentation.

---

## 22. Default Gateway
The default gateway is the router/interface a host uses to reach destinations outside its local network.

**Example:**

PC `192.168.1.10`  
Gateway `192.168.1.1`

Traffic for another network is sent toward the gateway.

---

## 23. NAT
NAT (Network Address Translation) modifies network addresses as traffic passes through a device.

A common use is allowing multiple private devices to share a public IPv4 address.

**Example:**

`192.168.1.10`  
`192.168.1.11`  
`192.168.1.12`

→ one public IPv4 address

**Cybersecurity:** NAT is not the same thing as a firewall and should not be treated as a complete security control.

---

## 24. Firewall
A firewall controls network traffic according to a security policy.

**Simple idea:**

Internet → Firewall → Internal Network

It can allow, block, or filter traffic based on configured rules.

---

## 25. VPN
A VPN creates a logical connection over another network and can use tunneling and cryptographic protection.

**Simple idea:**

Your device → encrypted/protected tunnel → VPN endpoint → destination

---

## 26. DMZ
A DMZ is a network segment placed between less-trusted external networks and a more-trusted internal network.

Public-facing systems may be placed in the DMZ so they are separated from internal systems.

---

## 27. HTTP and HTTPS

### HTTP
HTTP is an application-layer protocol used for web communication.

### HTTPS
HTTPS is HTTP protected using TLS.

**Common ports:**
- HTTP → `80/TCP`
- HTTPS → `443/TCP`

**Cybersecurity:** HTTPS protects data in transit between endpoints when TLS is correctly implemented.

---

## 28. SSH
SSH is a protocol used for secure remote access and other secure communication.

**Common port:** `22/TCP`

---

## 29. Private IPv4 Addresses

Common private IPv4 ranges:

- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

These are used inside private networks and are not directly routable on the public Internet.

---

## 30. Useful Windows Commands

```powershell
ipconfig
ping
tracert
arp -a
nslookup
netstat
route print
```

### What they show

`ipconfig` → interface/network configuration  
`ping` → reachability testing using ICMP  
`tracert` → path toward a destination  
`arp -a` → ARP cache  
`nslookup` → DNS queries  
`netstat` → network connections/listening endpoints  
`route print` → routing table

---

## 31. Useful Linux Commands

```bash
ip addr
ip route
ping
traceroute
ip neigh
ss
dig
```

### What they show

`ip addr` → interface addresses  
`ip route` → routing table  
`ping` → reachability testing  
`traceroute` → path toward a destination  
`ip neigh` → neighbor/ARP information  
`ss` → sockets and connections  
`dig` → DNS queries

---

# Quick Revision

**Network** → connected devices communicating

**IP** → network-layer addressing

**MAC** → local link/interface addressing

**Switch** → forwards frames on a LAN

**Router** → forwards packets between networks

**TCP** → reliable, ordered transport

**UDP** → lightweight datagram transport

**Port** → transport-layer endpoint

**DNS** → domain-name system

**DHCP** → automatic network configuration

**ARP** → IPv4 address → local MAC resolution

**ICMP** → control/error messages

**NAT** → translates network addresses

**Firewall** → filters traffic by policy

**VPN** → protected logical connection over another network

**DMZ** → separated perimeter network

---

# Cybersecurity Questions

1. What is the difference between an IP address and a MAC address?
2. Why does a device need a port?
3. What is the difference between a switch and a router?
4. Why is TCP considered reliable?
5. Why is UDP different from TCP?
6. What happens when you type `https://example.com`?
7. What does DNS do?
8. What does DHCP provide?
9. Why is ARP needed on an IPv4 LAN?
10. Why are open ports important in security?
11. What is the role of a firewall?
12. Why is NAT not the same as a firewall?
13. What is a subnet?
14. What is a default gateway?
15. What is the difference between a packet and a frame?
