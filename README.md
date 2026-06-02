# Breaking Into Pentesting — My Study Repo

So I'm on a mission to become a Junior Pentester, and this is where I keep everything — notes I've written, resources I've actually used, scripts I've built, and writeups from machines I've rooted. Think of it less like a curriculum and more like a map of where I've been and where I'm going.

This is very much a living thing. I update it as I go.

---

## The Certs I'm Gunning For

| Cert | Issuer | Why |
|------|--------|-----|
| **OSCP** | Offensive Security | The gold standard. Hands-on, brutal, worth it. |
| **CPTS** | Hack The Box | Solid structured path, great for building methodology |
| **PNPT** | TCM Security | Practical, realistic, and beginner-friendly |
| **CPENT** | EC-Council | Rounding it out with enterprise-level coverage |

---

## How I'm Approaching This

The plan is to run two tracks in parallel — fundamentals and scripting — before jumping into actual pentesting. You can't automate what you don't understand, and you can't understand what you can't navigate manually. So both run together.

```
Track 1: Core Fundamentals  ──┐
                               ├──▶  Phase 3: Real Pentesting
Track 2: Scripting         ──┘
```

Honestly, learning Bash while doing Linux made both click way faster than doing them sequentially. Same deal with PowerShell and Windows. Do yourself a favor — don't skip scripting until later.

---

## Phase 1 — Building the Foundation

Everything pentesting touches lives somewhere in these fundamentals. Don't rush through them. Networking especially — it shows up *everywhere*.

| # | Topic | My Notes |
|---|-------|----------|
| 1 | Linux Fundamentals | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Linux/1.%20Introduction%20to%20Linux.md) |
| 2 | Windows Fundamentals | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Windows/1.%20Introduction%20to%20Windows.md) |
| 3 | Cyber Security Intro & Terms | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Cyber%20Security%20Terms%20and%20Basics/1.%20Basic%20Terms.md) |
| 4 | Web Basics | [HTB Academy](https://academy.hackthebox.com) |
| 5 | Cryptography Basics | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Cryptography/1.%20Protecting%20Data%20in%20Motion%20or%20at%20Rest.md) |
| 6 | Computer Networking | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Networking/Day-1.md) |
| 7 | Windows Command Line | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Windows%20Command%20Line/1.%20Introduction.md) |
| 8 | Network Packet Analysis | HTB Academy Module |
| 9 | OSINT | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/OSINT/1.%20Open%E2%80%90source%20intelligence%20evolution%20and%20basics/1.%20INTRODUCTION.md) |

---

## Phase 2 — Scripting (Run This Alongside Phase 1)

Don't treat scripting as an afterthought. Pick it up while you're doing fundamentals — it makes the technical stuff stick, and you'll start automating tedious stuff sooner than you think.

### Bash
I went through [this full course on YouTube](https://youtu.be/Sx9zG7wa4FA?si=KfV3cI-WtUPstnN9) — covers everything from basic syntax to writing real automation. Solid starting point for anyone on Linux.

### PowerShell
[My own notes are here.](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/powershell/1.intro.md) Once you get into Active Directory attacks, PowerShell stops being optional. Get comfortable with it early.

---

## Phase 3 — Actual Pentesting

This is where things get real. Phases 1 and 2 feed directly into this. I'm going step by step, building methodology before tools.

| # | Topic | My Notes |
|---|-------|----------|
| 1 | Penetration Testing Process | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Penetration%20Testing/Pentesting%20Process/1.%20Preparation%20and%20Basic.md) |
| 2 | Getting Started with Pentesting | [Start here →](https://github.com/cristophercervantes/oscp-cpts-pnpt_prep/blob/main/Penetration%20Testing/Getting%20Started%20with%20Penetration%20Testing/1.%20Pentesting%20Basic%201.md) |

---

## Where I'm At Right Now

| Topic | Status |
|-------|--------|
| Linux Fundamentals | ✅ Done |
| Windows Fundamentals | ✅ Done |
| Cyber Security Intro & Terms | ✅ Done |
| Web Basics | ✅ Done |
| Windows Command Line | ✅ Done |
| Cryptography Basics | 🔄 In progress |
| Computer Networking | 🔄 In progress |
| Network Packet Analysis | 🔄 In progress |
| Bash Scripting | 🔄 In progress |
| PowerShell Scripting | 🔄 In progress |

---

## What's Coming Next

Once Phase 1 wraps up, I'll be adding notes and writeups for:

- Network Enumeration (Nmap and friends)
- Active Directory Attacks
- Web Application Pentesting
- Buffer Overflow
- Privilege Escalation — Linux & Windows
- CTF Writeups
- Lab Notes from HTB machines, TryHackMe rooms, and personal lab stuff

---

## Repo Layout

```
oscp-cpts-pnpt_prep/
│
├── Linux/
├── Windows/
├── Networking/
├── Cryptography/
├── OSINT/
├── Windows Command Line/
├── Cyber Security Terms and Basics/
├── powershell/
├── Penetration Testing/
│   ├── Pentesting Process/
│   └── Getting Started with Penetration Testing/
│
└── README.md
```

---

## A Quick Note

Everything here is for learning in legal, authorized environments — HTB, TryHackMe, personal labs. This stuff only gets used on systems I have explicit permission to touch. Don't be that guy.

---

*Started 2026 · [@cristophercervantes](https://github.com/cristophercervantes)*
