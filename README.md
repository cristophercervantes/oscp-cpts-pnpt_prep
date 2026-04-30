# OSCP / CPTS / PNPT Preparation

> My personal preparation repo for becoming a Junior Pentester. This covers everything I'm studying — notes, resources, scripts, and writeups — organized in the order I'm actually going through them.

This is a living document. I'll keep updating it as I progress.

---

## Target Certifications

- **OSCP** — Offensive Security Certified Professional
- **CPTS** — Certified Penetration Testing Specialist (HTB)
- **PNPT** — Practical Network Penetration Tester (TCM Security)

---

## Roadmap

The plan is split into two parallel tracks that you need to work at the same time:

1. **Core Fundamentals** — building the technical knowledge base
2. **Scripting** — learning automation and tooling along the way

Everything feeds into each other. Learning Linux while also picking up Bash scripting, learning Windows while getting comfortable with PowerShell — it makes the whole thing stick better.

---

## Phase 1 — Core Fundamentals

These are self-study modules. Resources are provided — the work is on me.

| # | Topic | Platform / Resource |
|---|-------|-------------------|
| 1 | Linux Fundamentals | [Hack The Box Academy](https://academy.hackthebox.com) |
| 2 | Windows Fundamentals | [Hack The Box Academy](https://academy.hackthebox.com) |
| 3 | Cyber Security Intro & Terms | HTB — Information Security Path |
| 4 | Web Basics | [Hack The Box Academy](https://academy.hackthebox.com) |
| 5 | Cryptography Basics | [Hacker Arise](https://www.hackers-arise.com) |
| 6 | Computer Networking | [Cisco Networking Academy](https://www.netacad.com) |
| 7 | Windows Command Line | HTB Academy Module |
| 8 | Network Packet Analysis | HTB Academy Module |

> Work through these in order if you're following along. Don't skip networking — it shows up everywhere.

---

## Phase 2 (Parallel) — Scripting

Learn these alongside the fundamentals above. Don't wait until after — scripting will make everything click faster.

### Bash Scripting
> Resource: [Full Bash Scripting Course — YouTube](https://youtu.be/Sx9zG7wa4FA?si=KfV3cI-WtUPstnN9)

Covers everything from basic shell syntax to writing real automation scripts. Essential for Linux-based pentesting work.

### PowerShell Scripting
> Resource: [PowerShell Scripting Playlist — YouTube](https://www.youtube.com/playlist?list=PLEoK7C0HvDQmY9uz_uJo0BTCC2XzSUF1h)

Core skill for Windows environments and Active Directory attacks. Gets very relevant once you move into AD pentesting.

---

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
│   └── (notes and methodologies about pentest from zero)
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
| Cryptography Basics | Completed |
| Computer Networking | Completed|
| Windows Command Line | Completed |
| Network Packet Analysis | Completed |
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

*Started: 2025 | Maintained by [@cristophercervantes](https://github.com/cristophercervantes)*
