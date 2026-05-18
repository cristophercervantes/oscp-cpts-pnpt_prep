# OSCP / CPTS / PNPT Preparation

> My personal preparation repo for becoming a Junior Pentester. This covers everything I'm studying — notes, resources, scripts, and writeups — organized in the order I'm actually going through them.

This is a living document. I'll keep updating it as I progress.

---

## Target Certifications

- **OSCP** — Offensive Security Certified Professional
- **CPTS** — Certified Penetration Testing Specialist (HTB)
- **PNPT** — Practical Network Penetration Tester (TCM Security)
- **CPENT** - Certified Penetration Testing Professional (EC-Council)

---

## Roadmap

The plan is split into two parallel tracks that you need to work at the same time:

1. **Core Fundamentals** — building the technical knowledge base
2. **Scripting** — learning automation and tooling along the way
3. **Real Pentest Begins** - Starting the official journey of Penetration Testing (Not parallel)

Everything feeds into each other. Learning Linux while also picking up Bash scripting, learning Windows while getting comfortable with PowerShell — it makes the whole thing stick better.

---

## Phase 1 — Core Fundamentals

These are self-study modules. Resources are provided — the work is on me.

| # | Topic | Resource |
|---|-------|-------------------|
| 1 | Linux Fundamentals | [Start learning from here](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Linux/1.%20Introduction%20to%20Linux.md) |
| 2 | Windows Fundamentals | [Start learning from here](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Windows/1.%20Introduction%20to%20Windows.md) |
| 3 | Cyber Security Intro & Terms | [Start learning from here](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Cyber%20Security%20Terms%20and%20Basics/1.%20Basic%20Terms.md) |
| 4 | Web Basics | [Hack The Box Academy](https://academy.hackthebox.com) |
| 5 | Cryptography Basics | [Start learning from here](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Cryptography/1.%20Some%20Network%20Security%20Concept.md) |
| 6 | Computer Networking | [Start learning from here](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Networking/Day-1.md) |
| 7 | Windows Command Line | [Start learning from here](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Windows%20Command%20Line/1.%20Introduction.md) |
| 8 | Network Packet Analysis | HTB Academy Module |
| 9 | OSINT | Coming |

> Work through these in order if you're following along. Don't skip networking — it shows up everywhere.

---

## Phase 2 (Parallel) — Scripting

Learn these alongside the fundamentals above. Don't wait until after — scripting will make everything click faster.

### Bash Scripting
> Resource: [Full Bash Scripting Course — YouTube](https://youtu.be/Sx9zG7wa4FA?si=KfV3cI-WtUPstnN9)

Covers everything from basic shell syntax to writing real automation scripts. Essential for Linux-based pentesting work.

### PowerShell Scripting
> Resource: [My own github repo](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/powershell/1.intro.md)

Core skill for Windows environments and Active Directory attacks. Gets very relevant once you move into AD pentesting.

---

## Phrase 3 - Penetration Testing

Starting learning about real penetration testing step by step
These are self-study modules. Resources are provided — the work is on me.

| # | Topic | Resource |
|---|-------|-------------------|
| 1 | Penetration Testing Process | [Start learning from here](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Penetration%20Testing/Pentesting%20Process/1.%20Preparation%20and%20Basic.md) |


##  Repo Structure

```
oscp-cpts-pnpt_prep/
│
├── fundamentals/
│   ├── linux/
│   ├── windows/
│   ├── networking/
│   ├── web-basics/
│   └── cryptography/
│
├── scripting/
│   ├── bash/
│   └── powershell/
│
├── Pentesting starts/
│   ├── Penetration Testing Process/
│
└── README.md
```

> Structure will grow as more phases get added.

---

##  Progress Tracker

| Topic | Status |
|-------|--------|
| Linux Fundamentals | Completed |
| Windows Fundamentals | Completed |
| Cyber Security Intro & Terms | Completed |
| Web Basics | Completed |
| Cryptography Basics | Ongoing |
| Computer Networking | Ongoing|
| Windows Command Line | Completed |
| Network Packet Analysis | Ongoing |
| Bash Scripting | Ongoing |
| PowerShell Scripting | Ongoing |

---

## Coming Soon

More phases will be added here as I finish Phase 1. Topics planned for later:

- Network Enumeration (Nmap, etc.)
- Active Directory Attacks
- Web Application Pentesting
- Buffer Overflow
- Privilege Escalation (Linux & Windows)
- CTF Writeups
- Lab Notes (HTB Machines, TryHackMe, etc.)

---

## Disclaimer

Everything in this repo is for **educational and ethical hacking purposes only**. All practice is done in legal, authorized environments (HTB, TryHackMe, personal labs). Never use these techniques against systems you don't have explicit permission to test.

---

*Started: 2026 | Maintained by [@cristophercervantes](https://github.com/cristophercervantes)*
