### Why Do We Need Protocols?

Just like two people can't communicate if they speak different languages, computers can't exchange data if they use different protocols.

**Early problem:**

```
Apple iMac                          IBM Server
[proprietary Apple protocols]  ≠   [proprietary IBM protocols]
              ✗ Cannot communicate
```

**Solution — Open Standards:**

```
MacBook        Linux Server       Android Phone      Windows PC
     \              |                  |              /
      └──────────── TCP/IP ────────────┘
              ✓ All can communicate
```

> A **protocol** is a set of rules defining how data is communicated between devices. A **standard** is an agreed-upon specification that describes how a protocol should work.
### Brief History

```
1960s ── ARPANET funded by US DoD (ARPA)
1969 ── ARPANET goes online (universities & labs)
         └── Used NCP (Network Control Program)
1974 ── Vint Cerf & Bob Kahn develop TCP
         └── Later split into TCP + IP
1983 ── ARPANET fully switches to TCP/IP (Jan 1st)
Today── TCP/IP runs the entire internet
```

**The two people who built the internet's foundation:**

- **Vint Cerf** — co-developer of TCP
- **Bob Kahn** — co-developer of TCP

### Who Makes the Standards?

|Organization|Full Name|What They Define|
|---|---|---|
|**IEEE**|Institute of Electrical and Electronics Engineers|Ethernet (802.3), Wi-Fi (802.11) — physical & local network standards|
|**IETF**|Internet Engineering Task Force|TCP, IP, UDP, HTTP, DNS — internet protocols|

IETF publishes standards as **RFCs (Requests for Comments)** — freely available online.

> Vendors like Cisco then **implement** these standards in their hardware.

### The Layered Model — Mail Example for easy understanding

Before jumping into TCP/IP, here's an analogy that makes it click:

```
You                Post Office A    Post Office B         Bob's House
 │                      │                │                     │
 │  Letter to Bob        │                │                     │
 │  ┌─────────────┐      │                │                     │
 │  │ Content     │      │                │                     │
 │  │ "Dear Bob"  │      │                │                     │
 │  ├─────────────┤      │                │                     │
 │  │ Recipient   │      │                │                     │
 │  │ "To: Bob"   │      │                │                     │
 │  ├─────────────┤      │                │                     │
 │  │ Address     │      │                │                     │
 │  │ Bob's house │      │                │                     │
 │  ├─────────────┤      │                │                     │
 │  │ Delivery    │──Car─┤──────Truck─────┤──────Truck──────────┤
 │  ├─────────────┤      │                │                     │
 │  │ Roads/Infra │══════════════════════════════════════════════
 │  └─────────────┘
```

Each layer has **one job** and doesn't worry about the others. The content of the letter doesn't change no matter how it gets delivered.

### The 5-Layer TCP/IP Model

```
┌─────────────────────────────────────────────────┐
│  Layer 5 — Application  (Layer 7 in OSI)        │
│  HTTP, HTTPS, FTP, DNS, SMTP                    │
├─────────────────────────────────────────────────┤
│  Layer 4 — Transport                            │
│  TCP, UDP                                       │
├─────────────────────────────────────────────────┤
│  Layer 3 — Internet / Network                   │
│  IP (v4 & v6), ICMP                             │
├─────────────────────────────────────────────────┤
│  Layer 2 — Local Network / Data Link            │
│  Ethernet, Wi-Fi                                │
├─────────────────────────────────────────────────┤
│  Layer 1 — Physical                             │
│  UTP cables, Fiber, Wi-Fi radio, NICs           │
└─────────────────────────────────────────────────┘
```

### What Each Layer Actually Does

#### Layer 1 — Physical

```
Sends and receives raw BITS as signals

Copper UTP  → electrical signals
Fiber optic → light signals
Wi-Fi       → radio signals

Components: cables, connectors, NICs, antennas
```

#### Layer 2 — Local Network (Data Link)

```
Delivers messages HOP-TO-HOP within a local network
Uses MAC addresses to identify interfaces

PC1 ──[hop 1]──► R1 ──[hop 2]──► R2 ──[hop 3]──► SRV1

Each hop = one delivery step
Switches DON'T count as hops — they extend the LAN

Protocols: Ethernet, Wi-Fi
Addressing: MAC addresses
```

#### Layer 3 — Internet (Network)

```
Delivers messages END-TO-END across multiple networks
Uses IP addresses

PC1 ────────────────────────────────────────► SRV1
     (doesn't care about hops in between)
     IP: 192.168.1.1                IP: 10.1.1.1

Routers operate at this layer
Protocols: IPv4, IPv6, ICMP
Addressing: IP addresses
```

#### Layer 4 — Transport

```
Delivers data to the correct APPLICATION PROCESS
Uses port numbers

SRV1 is running:
├── Web Server  → Port 80
└── File Server → Port 21

PC1 sends to port 80 → reaches web server ✓
PC1 sends to port 21 → reaches file server ✓

Protocols: TCP, UDP
Addressing: Port numbers
Runs mainly on the communicating HOSTS (not routers)
```

#### Layer 5 — Application

```
Defines how applications FORMAT, SEND, and INTERPRET data

Web browsing  → HTTP / HTTPS
File transfer → FTP / TFTP
Email         → SMTP / IMAP
DNS lookups   → DNS

Only the communicating hosts care about this layer
Routers and switches ignore it
```

### Real Network Example

```
PC1 ──── SW1 ──── R1 ──── R2 ──── SW2 ──── SRV1
(client)                               (web + file server)
```

**PC1 wants to reach SRV1's web server:**

|Layer|Question answered|Answer|
|---|---|---|
|App (L5)|What data am I sending?|HTTP request for web page|
|Transport (L4)|Which process on SRV1?|Port 80 (web server)|
|Internet (L3)|Which host?|SRV1's IP: 10.1.1.1|
|Local Net (L2)|Which next hop?|R1's MAC address|
|Physical (L1)|How do I send it?|Electrical signal over UTP|

### Encapsulation & Decapsulation

As data moves **down** the stack on the sender, each layer wraps it with a header (encapsulation). As it moves **up** the stack on the receiver, each layer unwraps it (decapsulation).

**Encapsulation (Sender — going DOWN):**

```
Application data
        ↓ Layer 4 adds header
[ L4 Header | Data ]  ← Segment (TCP) or Datagram (UDP)
        ↓ Layer 3 adds header
[ L3 Header | L4 Header | Data ]  ← Packet
        ↓ Layer 2 adds header + trailer
[ L2 Header | L3 Header | L4 Header | Data | L2 Trailer ]  ← Frame
        ↓ Layer 1 transmits as bits
10110010100110...  (signals over wire)
```

**Decapsulation (Receiver — going UP):**

```
10110010100110...  received as bits
        ↑ Layer 2 reads & removes L2 header + trailer
[ L3 Header | L4 Header | Data ]
        ↑ Layer 3 reads & removes L3 header
[ L4 Header | Data ]
        ↑ Layer 4 reads & removes L4 header
[ Data ]
        ↑ Application processes the data
```

### PDU Names — Protocol Data Units

This is what the message is called at each layer:

|Layer|PDU Name|Notes|
|---|---|---|
|Layer 4 (TCP)|**Segment**||
|Layer 4 (UDP)|**Datagram**||
|Layer 3|**Packet**|Most common term used in networking|
|Layer 2|**Frame**|What actually travels over the wire|

> **Payload** = the contents inside a PDU (everything except that layer's own header/trailer)

```
Frame:
┌──────────┬────────────────────────────┬──────────┐
│ L2 Header│      PAYLOAD               │L2 Trailer│
│          │  ┌──────────┬───────────┐  │          │
│          │  │ L3 Header│  PAYLOAD  │  │          │
│          │  │          │ ┌───────┐ │  │          │
│          │  │          │ │L4 Hdr │ │  │          │
│          │  │          │ │+ Data │ │  │          │
│          │  │          │ └───────┘ │  │          │
│          │  └──────────┴───────────┘  │          │
└──────────┴────────────────────────────┴──────────┘
```

### Layer Interactions

**Adjacent-layer interaction** — layers on the _same device_ working together:

```
App (L5) uses Transport (L4)'s service
Transport (L4) uses Internet (L3)'s service
Internet (L3) uses Local Network (L2)'s service
Local Network (L2) uses Physical (L1)'s service
```

**Same-layer interaction** — the _same layer_ communicating across devices:

```
PC1 App Layer  ←─────────────────────────────────► SRV1 App Layer
PC1 L4         ←─────────────────────────────────► SRV1 L4
PC1 L3         ←─────────────────────────────────► SRV1 L3
PC1 L2         ←────────────► R1 L2
                                R1 L2 ←────────────► R2 L2
                                                  R2 L2 ←──► SRV1 L2
```

### TCP/IP vs OSI Model

|OSI Layer #|OSI Name|TCP/IP (5-layer)|
|---|---|---|
|7|Application|Application|
|6|Presentation|↑ (merged into Application)|
|5|Session|↑ (merged into Application)|
|4|Transport|Transport|
|3|Network|Internet / Network|
|2|Data Link|Local Network / Data Link|
|1|Physical|Physical|

**Why OSI lost to TCP/IP:**

- OSI was designed top-down by committees — too complex, too late
- TCP/IP was open, practical, and already running on ARPANET
- TCP/IP won in the real world

**Reason for still using OSI:**

- Still used as a reference and teaching model
- "Layer 2", "Layer 3" etc. come from OSI numbering
- Common language among network engineers
