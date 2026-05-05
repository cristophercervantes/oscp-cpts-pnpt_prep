### What is a Network?

A **computer network** is a digital communications system that allows nodes to share resources.

That's the technical definition. Simply put — when two or more devices are connected and can talk to each other, that's a network. Even two PCs connected by a single cable counts.

### Network Nodes

A node is any device that participates in a network. Here are the core ones:

```
┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐
│ Router  │    │ Switch  │    │Firewall │    │ Server  │    │ Client  │
│   🔀    │    │   🔁    │    │  🛡️    │    │   🖥️   │    │  💻    │
└─────────┘    └─────────┘    └─────────┘    └─────────┘    └─────────┘
Connects       Connects        Filters         Provides        Accesses
networks       hosts in        traffic         services        services
together       same LAN
```

### 1. Client & Server

These two are defined in relation to each other.

```
        Request: "Send me image.jpg"
PC1 ─────────────────────────────────→ PC2
(Client)                               (Server)
        ←─────────────────────────────
        Response: sends image.jpg
```

|Device|Role|Definition|
|---|---|---|
|Client|Requester|A device that accesses a service made available by a server|
|Server|Provider|A device that provides functions or services for clients|

> **Important:** The same device can be both. Your phone is a client when watching YouTube, but a server when sending a file via AirDrop.

#### Real world example:

```
Your Device          The Internet          YouTube Server
   💻    ──────────────────────────────────→   🖥️
(Client)    "Send me this video"            (Server)
   💻    ←──────────────────────────────────   🖥️
           streams video data back
```
### 2. Switch

```
                        ┌──────────────┐
           PC1 ─────────┤              ├───────── PC3
           PC2 ─────────┤   Switch     ├───────── PC4
        Printer ─────────┤   (SW1)     ├───────── PC5
                        └──────────────┘
                         All in same LAN
```

**Characteristics:**

- Has many interfaces — usually **24 or more** ports
- Connects end hosts **within the same LAN**
- Forwards traffic **only within** the local network
- **Cannot** connect to other LANs or the internet on its own

> Think of a switch as the central hub of a room — everything in that room plugs into it.

### 3. Router

```
  New York LAN                              Tokyo LAN
┌─────────────┐                          ┌─────────────┐
│ PC1   PC2   │                          │  SRV1  SRV2 │
│   \   /     │                          │    \   /    │
│   SW1       │                          │    SW2      │
│    |        │      🌐 Internet          │     |       │
│   R1 ───────┼──────────────────────────┼─── R2       │
└─────────────┘                          └─────────────┘
```

**Characteristics:**

- Has **fewer ports** than a switch (designed for network-to-network, not host-to-host)
- Connects **separate networks** together
- Routes traffic **between LANs** and over the **internet**
- End hosts send traffic to their router when the destination is outside their LAN

### 4. Firewall

```
                    🚫 Attacker
                        |
                        ↓
  Internet ──→ [FW1 - Outside] ──→ Router ──→ [FW2 - Inside] ──→ LAN
                 Blocks bad              Blocks bad
                 traffic in              traffic inside
```

**Two placement options:**

```
Option A — Outside the router:
Internet → Firewall → Router → LAN

Option B — Inside the router:
Internet → Router → Firewall → LAN

Option C — Both (most secure):
Internet → Firewall → Router → Firewall → LAN
```

**Characteristics:**

- Monitors and **controls traffic** based on configured rules
- Explicitly allows or denies traffic
- Can be placed inside or outside the network
- **Next-Generation Firewalls (NGFW)** include advanced features like IPS (Intrusion Prevention System)

#### Network Firewall vs Host-based Firewall:

|Type|What it is|Where it runs|
|---|---|---|
|Network Firewall|Hardware device|Between networks|
|Host-based Firewall|Software application|On each individual PC|

> Both should be used together — hardware firewall for the network, software firewall on each device as an extra layer.

### Putting It All Together

```
                          🌐 INTERNET
                               |
                    ┌─────[Firewall]─────┐
                    |                    |
                 [Router R1]         [Router R2]
                    |                    |
                 [Switch SW1]        [Switch SW2]
                 /    |    \           /    \
               PC1   PC2  Printer   SRV1   SRV2

          ◄── New York LAN ──►    ◄─── Tokyo LAN ───►
```

**Data flow example — PC1 requests a file from SRV1:**

```
PC1 → SW1 → R1 → Internet → R2 → SW2 → SRV1
                                         ↓
PC1 ← SW1 ← R1 ← Internet ← R2 ← SW2 ← (sends file back)
```

