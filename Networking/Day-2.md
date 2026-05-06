### Bits & Speed — The Basics

Before cables make sense, you need to understand how data is measured.

**What is a bit?** A bit is a single value — either `0` or `1`. Everything in computing is just a long series of these.

**What is a byte?**

```
1 Byte = 8 Bits
[ 1 | 0 | 1 | 1 | 0 | 0 | 1 | 0 ]
```

**Network speed is always measured in bits per second — not bytes.**

```
1 Kilobit  (Kbps) =          1,000 bits
1 Megabit  (Mbps) =      1,000,000 bits
1 Gigabit  (Gbps) =  1,000,000,000 bits
1 Terabit  (Tbps) = 1,000,000,000,000 bits
```

> A Gigabyte (storage) is 8× larger than a Gigabit (speed). Don't mix them up.

Data travels one bit at a time down a wire:

```
Sending 1 Byte:
Wire → [1] → [0] → [1] → [1] → [0] → [0] → [1] → [0] → destination
         bit by bit, not all at once
```

### Ethernet Standards (Copper)

All defined under **IEEE 802.3**. These are what you need to memorize:

|Speed|Common Name|Standard|Informal Name|Max Length|
|---|---|---|---|---|
|10 Mbps|Ethernet|802.3i|10BASE-T|100 m|
|100 Mbps|Fast Ethernet|802.3u|100BASE-T|100 m|
|1 Gbps|Gigabit Ethernet|802.3ab|1000BASE-T|100 m|
|10 Gbps|10 Gig Ethernet|802.3an|10GBASE-T|100 m|

**Naming breakdown:**

```
  1000  BASE  T
  ────  ────  ─
  Speed Base- Twisted
        band  pair
```

> All copper twisted pair cables max out at **100 meters**.

### UTP Cables

**UTP = Unshielded Twisted Pair**

```
        ┌─────────────────────┐
        │  Pair 1 (pins 1,2)  │ ══╗
        │  Pair 2 (pins 3,6)  │ ══╣  twisted together
        │  Pair 3 (pins 4,5)  │ ══╣  inside the cable
        │  Pair 4 (pins 7,8)  │ ══╝
        └─────────────────────┘
         8 wires total → 8 pins on RJ-45
```

- **Unshielded** — no metal shield around the wires, can be affected by EMI
- **Twisted** — the twisting itself helps reduce electromagnetic interference
- Connects via **RJ-45** connector (the clip-in plug you know from ethernet cables)

**How many wires are used per standard?**

|Standard|Pairs Used|Wires Used|
|---|---|---|
|10BASE-T & 100BASE-T|2 pairs|4 wires (pins 1,2,3,6)|
|1000BASE-T & 10GBASE-T|4 pairs|8 wires (all pins)|

### Pin Diagrams & Full Duplex

For 10BASE-T and 100BASE-T, only pins **1, 2, 3, 6** are used.

**PC → Switch connection:**

```
        PC                          Switch
  Pin 1 ──── Tx ──────────────── Rx ──── Pin 1
  Pin 2 ──── Tx ──────────────── Rx ──── Pin 2
  Pin 3 ──── Rx ──────────────── Tx ──── Pin 3
  Pin 6 ──── Rx ──────────────── Tx ──── Pin 6
```

**Full-Duplex** = both devices send and receive at the same time with no collision because they use separate wire pairs for each direction.

**Who transmits on which pins?**

|Device|Transmit (Tx)|Receive (Rx)|
|---|---|---|
|PC|Pins 1, 2|Pins 3, 6|
|Router|Pins 1, 2|Pins 3, 6|
|Firewall|Pins 1, 2|Pins 3, 6|
|**Switch**|**Pins 3, 6**|**Pins 1, 2**|

> Switch is the odd one out — it's the opposite of everything else.

### Straight-Through vs Crossover Cable

**Straight-Through Cable** — pin 1 connects to pin 1, pin 2 to pin 2, etc.

```
End A                    End B
Pin 1 ───────────────── Pin 1
Pin 2 ───────────────── Pin 2
Pin 3 ───────────────── Pin 3
Pin 6 ───────────────── Pin 6
```

Use when connecting **different** device types (PC↔Switch, Router↔Switch):

```
PC    ──[straight-through]── Switch   works
Router──[straight-through]── Switch   works
```

**Crossover Cable** — pairs are reversed on each end.

```
End A                    End B
Pin 1 ───────────────── Pin 3
Pin 2 ───────────────── Pin 6
Pin 3 ───────────────── Pin 1
Pin 6 ───────────────── Pin 2
```

Use when connecting **same** device types (Router↔Router, Switch↔Switch, PC↔PC):

```
Router ──[crossover]── Router   works
Switch ──[crossover]── Switch   works
PC     ──[crossover]── PC       works
PC     ──[crossover]── Router   works (both transmit on 1,2)
```

**Why crossover works:**

```
Router A                        Router B
Tx: Pin 1,2 ──────────────── Rx: Pin 3,6  
Rx: Pin 3,6 ──────────────── Tx: Pin 1,2  
```

### Auto MDI-X

Modern devices don't make you think about this at all.

```
Switch A ──[straight-through]── Switch B
              ↓
     Auto MDI-X detects the issue
     and automatically adjusts pins
              ↓
         Works fine 
```

> If a device says **Auto MDI-X** on its ports, you can use either cable type and it figures it out. Most modern equipment has this. Old equipment does not.

### Gigabit & 10G — Bidirectional Pairs

For **1000BASE-T** and **10GBASE-T**, all 8 wires are used AND each pair is **bidirectional** — meaning a single pair handles both transmit and receive simultaneously. This is part of how they achieve such high speeds.

```
Pins 1,2  → bidirectional
Pins 3,6  → bidirectional
Pins 4,5  → bidirectional
Pins 7,8  → bidirectional
```

### Fiber Optic Cables

When copper won't do — too far, too much interference, or need more security.

**How it works:**

```
Device A                              Device B
  [SFP] ──── glass fiber ──────────── [SFP]
  Tx  ──────────────────────────────→ Rx
  Rx  ←────────────────────────────── Tx
       (two separate cables/strands)
```

Instead of electrical signals, fiber uses **light through glass**.

**Cable structure (inside out):**

```
     ┌──────────────────────┐
  1  │  Fiberglass Core     │  ← light travels here
  2  │  Reflective Cladding │  ← bounces light inward
  3  │  Protective Buffer   │  ← prevents fiber from breaking
  4  │  Outer Jacket        │  ← outer protection
     └──────────────────────┘
```

### Multimode vs Single-Mode Fiber

```
MULTIMODE                          SINGLE-MODE
─────────────────────────          ─────────────────────────
Wider core                         Narrower core
Multiple light angles (modes)      Single light angle (mode)
LED-based transmitter              Laser-based transmitter
Cheaper                            More expensive
Shorter distances                  Longer distances
Good for: building to building     Good for: city to city
```

**Visually:**

```
Multimode:                  Single-mode:
  ╲  ╱  ╲  ╱               ──────────────→
   ╲╱    ╲╱    (bounces)    (straight line)
```

### Fiber Optic Standards

|Standard|Speed|Cable Type|Max Distance|
|---|---|---|---|
|1000BASE-LX|1 Gbps|Multimode|550 m|
|1000BASE-LX|1 Gbps|Single-mode|5 km|
|10GBASE-SR|10 Gbps|Multimode|400 m|
|10GBASE-LR|10 Gbps|Single-mode|10 km|
|10GBASE-ER|10 Gbps|Single-mode|30 km|

All 10G standards defined under **IEEE 802.3ae**.

### UTP vs Fiber 

|Feature|UTP Copper|Fiber Optic|
|---|---|---|
|Cost|Cheaper|More expensive|
|Max distance|~100 m|Up to 30+ km|
|EMI vulnerability|Yes|No|
|Signal leakage|Yes (security risk)|No|
|Connector|RJ-45 (cheap)|SFP transceiver (expensive)|
|Best for|End hosts in same floor/building|Building-to-building, long distance|

