# 🌐 Computer Networks - MCS-218
Master of Computer Applications (MCA) - Core Networking Course

This folder contains comprehensive networking study materials, protocol documentation, and learning resources for MCS-218.

---

## 📚 Course Overview
Computer Networks is essential for understanding how systems communicate. This course covers:

✓ Network fundamentals and architecture
✓ OSI and TCP/IP models
✓ Network protocols at different layers
✓ Routing and switching
✓ Network security and cryptography
✓ DNS and application layer protocols
✓ Network troubleshooting

---

## 🎯 Learning Objectives
By the end of this course, you will:

✅ Understand network architecture and layers
✅ Master TCP/IP protocol suite
✅ Design and troubleshoot networks
✅ Implement network security
✅ Understand DNS and DHCP
✅ Work with routing protocols
✅ Analyze network traffic
✅ Optimize network performance

---

## 📖 Topics Covered

### 1. Network Fundamentals 🔧
```
├── Introduction to Networks
├── Network Goals and Applications
├── Types of Networks
│   ├── LAN (Local Area Network)
│   ├── WAN (Wide Area Network)
│   ├── MAN (Metropolitan Area Network)
│   ├── PAN (Personal Area Network)
│   └── VPN (Virtual Private Network)
├── Network Topologies
│   ├── Bus Topology
│   ├── Star Topology
│   ├── Ring Topology
│   ├── Mesh Topology
│   └── Tree Topology
├── Network Protocols
├── Switching vs Routing
└── Network Models
```

**Key Concepts:**
- Networks enable communication between devices
- LAN: High-speed, limited geographical area
- WAN: Slow, covers large distances
- Topology: Physical or logical arrangement
- Protocols: Rules for communication

**Network Types Comparison:**

| Type | Range | Speed | Cost | Coverage |
|------|-------|-------|------|----------|
| PAN | 10 m | 1-2 Mbps | Low | Personal |
| LAN | 1-10 km | 100 Mbps | Low | Office/Home |
| MAN | 10-100 km | 10 Mbps | Medium | City |
| WAN | Global | 1-100 Mbps | High | Countries |

---

### 2. OSI Model (7 Layers) 🏗️
```
┌─────────────────────────────────────────────┐
│ 7. APPLICATION LAYER                        │
│    HTTP, HTTPS, FTP, SMTP, DNS, Telnet, SSH│
├─────────────────────────────────────────────┤
│ 6. PRESENTATION LAYER                       │
│    Encryption, Compression, Translation    │
├─────────────────────────────────────────────┤
│ 5. SESSION LAYER                            │
│    Session Management, Dialog Control      │
├─────────────────────────────────────────────┤
│ 4. TRANSPORT LAYER                          │
│    TCP, UDP, SCTP                          │
├─────────────────────────────────────────────┤
│ 3. NETWORK LAYER                            │
│    IP, ICMP, IGMP, Routing                 │
├─────────────────────────────────────────────┤
│ 2. DATA LINK LAYER                          │
│    Ethernet, PPP, MAC, Switching           │
├─────────────────────────────────────────────┤
│ 1. PHYSICAL LAYER                           │
│    Cables, Hubs, Repeaters, Signals        │
└─────────────────────────────────────────────┘
```

**OSI Layer Details:**

| Layer | Name | Function | Devices | Protocols |
|-------|------|----------|---------|----------|
| 7 | Application | User interface | None | HTTP, FTP, DNS |
| 6 | Presentation | Data conversion | None | SSL, TLS |
| 5 | Session | Connection management | None | RPC |
| 4 | Transport | End-to-end delivery | None | TCP, UDP |
| 3 | Network | Routing, IP addressing | Router | IP, ICMP |
| 2 | Data Link | MAC addressing, switching | Switch | Ethernet |
| 1 | Physical | Transmission media | Hub | Cables |

**PDU (Protocol Data Unit) at Each Layer:**
```
Application → Message
Transport → Segment (TCP) / Datagram (UDP)
Network → Packet
Data Link → Frame
Physical → Bits
```

---

### 3. TCP/IP Model (4-5 Layers) 📡
```
┌──────────────────────────────────────────┐
│ 4/5. APPLICATION LAYER                   │
│      HTTP, HTTPS, FTP, SMTP, DNS, etc.  │
├──────────────────────────────────────────┤
│ 3. TRANSPORT LAYER                       │
│      TCP (Reliable), UDP (Fast)          │
├──────────────────────────────────────────┤
│ 2. INTERNET LAYER                        │
│      IP, ICMP, IGMP, ARP                │
├──────────────────────────────────────────┤
│ 1. LINK/PHYSICAL LAYER                   │
│      Ethernet, PPP, MAC                  │
└──────────────────────────────────────────┘
```

**Advantages over OSI:**
- Simpler (4-5 layers vs 7)
- Practical implementation
- Still widely used today
- Better separation of concerns

---

### 4. Physical Layer 🔌
```
├── Transmission Media
│   ├── Twisted Pair
│   │   ├── UTP (Unshielded)
│   │   └── STP (Shielded)
│   ├── Coaxial Cable
│   ├── Fiber Optic
│   └── Wireless (Radio, Microwave)
├── Physical Devices
│   ├── Repeater
│   ├── Hub
│   └── Network Interface Card (NIC)
├── Signal Types
│   ├── Analog Signal
│   └── Digital Signal
└── Transmission Methods
    ├── Simplex (One direction)
    ├── Half-Duplex (Both, not simultaneously)
    └── Full-Duplex (Both, simultaneously)
```

**Transmission Media Comparison:**

| Media | Speed | Distance | Cost | EMI |
|-------|-------|----------|------|-----|
| Twisted Pair | 100 Mbps-10 Gbps | 100m | Low | High |
| Coaxial | 10 Mbps-100 Mbps | 500m | Medium | Medium |
| Fiber Optic | 100 Gbps | 100 km | High | None |

---

### 5. Data Link Layer (Layer 2) 🔗
```
├── MAC (Media Access Control)
│   ├── MAC Addressing (48-bit)
│   ├── ARP (Address Resolution Protocol)
│   └── RARP (Reverse ARP)
├── Switching
│   ├── Circuit Switching
│   ├── Message Switching
│   └── Packet Switching
├── Ethernet
│   ├── 10BASE-T
│   ├── 100BASE-TX (Fast Ethernet)
│   └── 1000BASE-T (Gigabit)
├── PPP (Point-to-Point Protocol)
└── HDLC (High-level Data Link Control)
```

**MAC Address Format:**
```
48 bits = 6 octets
Format: XX:XX:XX:XX:XX:XX
Example: 00:1A:2B:3C:4D:5E

First 24 bits: OUI (Organizationally Unique Identifier)
Last 24 bits: Device-specific
```

**ARP Process (IP to MAC Resolution):**
```
1. Host A has IP of Host B, but needs MAC
2. Host A broadcasts ARP Request
3. Host B recognizes its IP, sends ARP Reply with MAC
4. Host A receives MAC and adds to ARP table
5. Now A can send frames to B
```

---

### 6. Network Layer (Layer 3) 🌐
```
├── IP Protocol
│   ├── IPv4 Addressing
│   │   ├── Classes (A, B, C, D, E)
│   │   ├── Subnetting
│   │   ├── CIDR Notation
│   │   └── Private Addresses
│   └── IPv6 Addressing
│       ├── 128-bit addresses
│       └── Advantages
├── ICMP (Internet Control Message Protocol)
│   ├── Ping
│   ├── Traceroute
│   └── Unreachable messages
├── Routing
│   ├── Static Routing
│   ├── Dynamic Routing
│   └── Routing Protocols
├── IGMP (Internet Group Management Protocol)
└── Router and Routing Tables
```

**IPv4 Address Classes:**

| Class | Range | First Octet | Hosts | Usage |
|-------|-------|-------------|-------|-------|
| A | 0-127 | 0-127 | 16M | Large networks |
| B | 128-191 | 128-191 | 64K | Medium networks |
| C | 192-223 | 192-223 | 254 | Small networks |
| D | 224-239 | 224-239 | N/A | Multicast |
| E | 240-255 | 240-255 | N/A | Reserved |

**IPv4 Address Format:**
```
32 bits = 4 octets
Format: XXX.XXX.XXX.XXX
Example: 192.168.1.1

Network | Host
```

**Subnetting Example:**
```
IP: 192.168.1.0/24
/24 means first 24 bits are network

Subnet Mask: 255.255.255.0
Network: 192.168.1.0
Broadcast: 192.168.1.255
Usable IPs: 192.168.1.1 to 192.168.1.254
Total Hosts: 254
```

---

### 7. Transport Layer (Layer 4) 📨
```
├── TCP (Transmission Control Protocol)
│   ├── Connection-oriented
│   ├── Reliable delivery
│   ├── Three-way Handshake
│   │   ├── SYN
│   │   ├── SYN-ACK
│   │   └── ACK
│   ├── Flow Control
│   ├── Congestion Control
│   └── Four-way Teardown
├── UDP (User Datagram Protocol)
│   ├── Connectionless
│   ├── Fast delivery
│   ├── No connection setup
│   └── No error checking
├── SCTP (Stream Control Transport Protocol)
└── DCCP (Datagram Congestion Control Protocol)
```

**TCP vs UDP Comparison:**

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented | Connectionless |
| Reliability | Reliable | Unreliable |
| Ordering | In-order delivery | No order guarantee |
| Speed | Slower | Faster |
| Header Size | 20-60 bytes | 8 bytes |
| Flow Control | Yes | No |
| Use Cases | Web, Email, FTP | Video, DNS, Gaming |

**TCP Three-Way Handshake:**
```
Client                                Server
  |                                     |
  |------------ SYN (seq=x) ----------->|
  |                                     |
  |<----- SYN-ACK (seq=y, ack=x+1)-----|
  |                                     |
  |------- ACK (seq=x+1, ack=y+1)------>|
  |                                     |
  |-------- Connection Established ----->|
  |                                     |
```

**TCP Teardown (Four-Way):**
```
Client                                Server
  |                                     |
  |-------------- FIN ----------------->|
  |                                     |
  |<------------- ACK ----------------|
  |                                     |
  |<------------- FIN ----------------|
  |                                     |
  |-------------- ACK ----------------->|
  |                                     |
  |-------- Connection Closed ---------->|
```

**Port Numbers:**
```
Well-Known Ports (0-1023)
- Port 20: FTP Data
- Port 21: FTP Control
- Port 22: SSH
- Port 23: Telnet
- Port 25: SMTP
- Port 53: DNS
- Port 80: HTTP
- Port 110: POP3
- Port 143: IMAP
- Port 443: HTTPS

Registered Ports (1024-49151)
Dynamic/Private (49152-65535)
```

---

### 8. Application Layer (Layer 7) 🖥️
```
├── DNS (Domain Name System)
│   ├── Name Resolution
│   ├── DNS Records
│   │   ├── A (IPv4)
│   │   ├── AAAA (IPv6)
│   │   ├── MX (Mail)
│   │   ├── CNAME (Alias)
│   │   ├── TXT
│   │   └── NS (Nameserver)
│   ├── Recursive Query
│   ├── Iterative Query
│   └── DNS Caching
│
├── HTTP/HTTPS
│   ├── Request Methods
│   │   ├── GET
│   │   ├── POST
│   │   ├── PUT
│   │   ├── DELETE
│   │   ├── HEAD
│   │   └── OPTIONS
│   ├── Status Codes
│   │   ├── 1xx (Info)
│   │   ├── 2xx (Success)
│   │   ├── 3xx (Redirect)
│   │   ├── 4xx (Client Error)
│   │   └── 5xx (Server Error)
│   ├── Headers
│   └── HTTPS (HTTP + SSL/TLS)
│
├── Email Protocols
│   ├── SMTP (Send Mail)
│   ├── POP3 (Receive Mail)
│   └── IMAP (Advanced Mail)
│
├── File Transfer
│   ├── FTP (File Transfer Protocol)
│   ├── SFTP (SSH FTP)
│   └── TFTP (Trivial FTP)
│
├── Remote Access
│   ├── Telnet
│   └── SSH (Secure Shell)
│
└── Other Protocols
    ├── VoIP (Voice over IP)
    ├── SIP (Session Initiation Protocol)
    └── RTMP (Real Time Messaging Protocol)
```

**DNS Query Process:**
```
1. User types URL (www.example.com)
2. Browser checks its cache
3. Queries ISP's Recursive Resolver
4. Resolver queries Root Nameserver
5. Root NS directs to TLD Nameserver
6. TLD NS directs to Authoritative NS
7. Authoritative NS returns IP address
8. IP returned through the chain
9. Browser receives IP, connects to website
```

**HTTP Status Codes (Common):**
```
2xx Success:
- 200 OK
- 201 Created
- 204 No Content

3xx Redirection:
- 301 Moved Permanently
- 302 Found (Temporary redirect)
- 304 Not Modified (Cached)

4xx Client Error:
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found

5xx Server Error:
- 500 Internal Server Error
- 502 Bad Gateway
- 503 Service Unavailable
```

---

### 9. Network Security & Cryptography 🔐
```
├── Cryptography Basics
│   ├── Symmetric Encryption
│   │   ├── DES (Data Encryption Standard)
│   │   ├── AES (Advanced Encryption Standard)
│   │   └── 3DES
│   │
│   ├── Asymmetric Encryption
│   │   ├── RSA
│   │   ├── Diffie-Hellman
│   │   └── ECC (Elliptic Curve)
│   │
│   ├── Hash Functions
│   │   ├── MD5 (Deprecated)
│   │   ├── SHA-1 (Deprecated)
│   │   ├── SHA-256 (Current)
│   │   └── SHA-512
│   │
│   └── Digital Signatures
│       └── Public Key + Hash
│
├── SSL/TLS Protocols
│   ├── HTTPS Implementation
│   ├── SSL Handshake
│   ├── Certificates
│   └── Certificate Authority (CA)
│
├── Network Firewalls
│   ├── Packet Filtering
│   ├── Stateful Inspection
│   ├── Proxy Firewall
│   └── Application Gateway
│
├── VPN (Virtual Private Network)
│   ├── Tunneling
│   ├── Encryption
│   └── Authentication
│
└── Authentication & Authorization
    ├── Username/Password
    ├── Multi-factor Authentication
    ├── Public Key Infrastructure
    └── Kerberos
```

**Encryption Comparison:**

| Type | Key Size | Speed | Security | Use Case |
|------|----------|-------|----------|----------|
| DES | 56-bit | Fast | Low | Legacy |
| 3DES | 168-bit | Medium | Medium | Legacy |
| AES | 128-256 bit | Fast | High | Current |
| RSA | 2048+ bit | Slow | High | Key exchange |

**SSL/TLS Handshake (Simplified):**
```
Client                              Server
  |                                   |
  |------- ClientHello (ciphers)----->|
  |                                   |
  |<-- ServerHello (certificate) ----|
  |                                   |
  |-- Key Exchange (encrypted) ------>|
  |                                   |
  |<---- Finished -------------------||
  |                                   |
  |------- Finished ----------------->|
  |                                   |
  |------ HTTPS Connection Ready ----->|
```

---

## 💻 Practical Exercises

### Beginner Level 🟢
- IP address calculation
- Subnet mask determination
- OSI layer identification
- MAC address format
- Port number identification

### Intermediate Level 🟡
- Network design
- Subnetting problems
- DNS queries
- Routing table analysis
- Protocol analysis

### Advanced Level 🔴
- Network troubleshooting
- Packet analysis (Wireshark)
- VPN configuration
- Firewall rules
- Security implementation

---

## 📊 Progress Tracking

| Topic | Status | Level | Notes |
|-------|--------|-------|-------|
| Network Fundamentals | ✅ Completed | Beginner | Foundation solid |
| OSI Model | ✅ Completed | Beginner | 7 layers mastered |
| TCP/IP Model | ✅ Completed | Beginner | 4-5 layers understood |
| Physical Layer | ⏳ In Progress | Intermediate | Media types covered |
| Data Link Layer | ⏳ In Progress | Intermediate | MAC and Ethernet done |
| Network Layer | ⏳ In Progress | Intermediate | IP addressing pending |
| Transport Layer | ✅ Completed | Intermediate | TCP vs UDP clear |
| Application Layer | ✅ Completed | Intermediate | DNS, HTTP understood |
| Security | ✅ Completed | Advanced | Cryptography mastered |

**Overall Progress: 60/100** 📈

---

## 📚 Recommended Resources

### Online Tutorials
- [GeeksforGeeks Networking](https://www.geeksforgeeks.org/computer-networks/)
- [Khan Academy Networking](https://www.khanacademy.org/)
- [Cisco Learning Network](https://learningnetwork.cisco.com/)
- [Coursera Networking](https://www.coursera.org/)

### Books
- "Computer Networking: A Top-Down Approach" by Kurose & Ross - **Best for beginners**
- "Computer Networks" by Tanenbaum & Wetherall - **Comprehensive**
- "TCP/IP Illustrated" by Stevens - **Advanced**
- "CCNA Study Guide" by Todd Lammle - **Cisco certification**

### Tools & Platforms
- **Wireshark** - Packet analyzer
- **Cisco Packet Tracer** - Network simulator
- **GNS3** - Network emulator
- **ifconfig/ipconfig** - Network configuration
- **ping, traceroute, nslookup** - Network tools

### Certifications
- **CompTIA A+** - IT fundamentals
- **CompTIA Network+** - Networking basics
- **Cisco CCNA** - Industry standard
- **CCNP** - Advanced routing

---

## 🛠️ How to Use This Folder

1. **Study Theory** - Read documentation thoroughly
2. **Understand Models** - Grasp OSI and TCP/IP models
3. **Learn Protocols** - Study each layer's protocols
4. **Practice Calculations** - IP addressing, subnetting
5. **Use Tools** - Analyze traffic with Wireshark
6. **Design Networks** - Use Packet Tracer or GNS3
7. **Troubleshoot** - Identify and fix issues
8. **Document** - Keep learning notes

---

## 💡 Study Tips

✨ **Layer-by-Layer Learning** - Master each OSI layer completely
✨ **Protocol Deep Dive** - Understand each protocol thoroughly
✨ **Hands-on Practice** - Use network simulators
✨ **Visual Learning** - Draw network diagrams
✨ **Memorize Models** - OSI and TCP/IP are foundational
✨ **Practice Calculations** - IP subnetting is important
✨ **Analyze Traffic** - Use Wireshark to see real protocols
✨ **Build Networks** - Use Packet Tracer for practice

---

## 🎯 Common Mistakes to Avoid

❌ Confusing TCP with IP
❌ Mixing up OSI and TCP/IP layers
❌ Not understanding address resolution
❌ Incorrect subnetting calculations
❌ Forgetting encryption importance
❌ Not learning packet structure
❌ Ignoring protocol timing
❌ Neglecting security concepts

---

## 📝 Quick Reference

### Important Protocols
```
Layer 7 (Application): HTTP, HTTPS, FTP, SMTP, DNS, SSH, Telnet
Layer 6 (Presentation): SSL, TLS, JPEG, MPEG
Layer 5 (Session): RPC, NetBIOS
Layer 4 (Transport): TCP, UDP, SCTP
Layer 3 (Network): IP, ICMP, IGMP, ARP
Layer 2 (Data Link): Ethernet, PPP, Frame Relay
Layer 1 (Physical): Cables, Hubs, Modems
```

### Default Ports
```
SSH: 22
Telnet: 23
DNS: 53
HTTP: 80
POP3: 110
IMAP: 143
HTTPS: 443
SMTP: 587 (TLS) / 465 (SSL)
```

---

## 🏆 Learning Milestones

- **Week 1-2** ✅ Network Fundamentals & OSI Model
- **Week 3-4** ✅ TCP/IP & Physical Layer
- **Week 5-6** ✅ Data Link & Network Layers
- **Week 7-8** ✅ Transport Layer & Protocols
- **Week 9-10** ✅ Application Layer & DNS
- **Week 11-12** ✅ Security & Cryptography
- **Week 13-14** ✅ Troubleshooting & Practice

---

## 📞 Need Help?

📧 **Email:** tripti.m2026@gmail.com
🔗 **LinkedIn:** https://www.linkedin.com/in/tripti-mishra-4a68881ba/
💻 **GitHub:** https://github.com/Tripti-m-ishra

---

*Master networking, master the digital world!* 🌐

**Last Updated:** June 5, 2026
**Next Review:** June 12, 2026
**Performance Grade:** A- (Very Good)