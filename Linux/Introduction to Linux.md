# Linux is a Kernel 
The word "Linux" is confusing because its meaning changes depending on who's talking. Technically, Linux is just the kernel. The kernel is the central brain of the computer; it's the first program that loads when you boot up, and it stays running the entire time, managing the hardware, memory, and all other processes. It's the core controller.

This complete system is more accurately called **GNU/Linux**. It's a combination: the **Linux kernel** at its center, surrounded by a huge collection of **GNU software** (like shells, compilers, and editors) that makes the system usable.

**The Backstory: UNIX**  
To get Linux, you have to start with UNIX. UNIX was created in the 1970s at AT&T Bell Labs. Its big innovation was being written in the C programming language, which made it portable—it could be adapted to run on different types of computer hardware, unlike most systems at the time. It became very popular in universities.

Over time, UNIX splintered into many different versions. Today, "UNIX" is both a technical standard and a trademark owned by an industry group called **The Open Group**. Only software they officially approve can call itself "UNIX."

**The Birth of the Linux Kernel**  
In 1991, a student named **Linus Torvalds** at the University of Helsinki was tinkering with MINIX, a simplified UNIX-like system used for teaching. He got frustrated by its licensing and limitations. So, as a hobby project, he decided to write his own kernel. He didn't set out to create a whole OS, just the core.

(Trivia: He originally called it "Freax." The administrator of the server where he shared his code renamed the project directory to "Linux," a mix of "Linus" and "UNIX," and the name stuck forever.)

**The GNU Project's Role**  
Running parallel to this was the **GNU Project**, started by **Richard Stallman** in 1983. Their ambitious goal was to create a complete, free operating system that worked like UNIX. While they struggled to finish their own kernel, they were incredibly successful at building all the essential tools that wrap around a kernel: things like the GCC compiler, the Bash shell, and core utilities. These tools were all freely available.

**The Perfect Combination**  
Linus had a working kernel. The GNU project had a mountain of mature, free tools. Developers combined them. The Linux kernel provided the core, and the GNU tools provided the complete environment users interact with. This partnership created the first truly viable, free, UNIX-like operating system: **GNU/Linux**.

Linux was designed to meet all the technical specifications of UNIX. However, it has never been submitted for or passed the official certification by The Open Group. Therefore, legally and technically, **Linux is not UNIX**. It is **UNIX-like**. This is a crucial distinction in formal contexts, even though they function very similarly.

## Linux is Open Source
Open source is a different worldview. It is **source-centric**. The core philosophy is that you have the right to obtain the **source code** of the software you use. More than that, you have the right to study it, modify it, and adapt it for your own needs. This creates transparency and empowers the user.

The source code can be written in many languages. Linus chose to write Linux in **C**.
- C is powerful and relatively easy to learn.
- It has a direct historical link to UNIX, giving Linux instant credibility and compatibility with existing concepts.
- Most importantly, C is a **systems programming language**. It gives the programmer fine-grained control over hardware, which is essential for an efficient kernel.

**Linux Distribution (Distro)**
- **What it is:** A complete, ready-to-install operating system package built around the Linux kernel.
- **What it contains:**
    - **Linux Kernel** (the core)
    - **GNU Tools & Core Utilities** (the base system)
    - **Applications** (user software like browsers, office suites)
    - **Package Manager** (tool for installing/removing software)
    - **Installation & Setup Tools**
        
- **Analogy:** A Linux distribution is like a **complete car**. The kernel is the engine, GNU tools are the chassis and basic controls, and the apps are the seats, stereo, and air conditioning. The distribution puts it all together and delivers it to you.

**Package Manager**
- **Definition:** A core tool in a distribution that handles the installation, updating, removal, and management of software packages.
- **Why it's important:** It's the primary way you get and manage software on Linux. It automatically handles **dependencies** (other required software) for you.
- **Major Types (a key difference between distros):**
    - **`apt` / `dpkg`**: Used by Debian, Ubuntu, and derivatives.
    - **`yum` / `dnf` / `rpm`**: Used by Red Hat, Fedora, CentOS, and derivatives.

**Major Distribution Families (Lineages)**  
Almost all distros trace their roots to one of these three. This determines their core design, tools, and philosophy.
1. **Debian**
    - **Philosophy:** Strong commitment to free software principles and community governance.
    - **Package Manager:** `apt` / `dpkg`
    - **Notable Derivatives:** **Ubuntu** (the most popular desktop distro), Linux Mint.
        
2. **Red Hat**
    - **Philosophy:** Enterprise-focused, commercially supported, stable.
    - **Package Manager:** Originally `rpm`/`yum`, now `dnf`.
    - **Notable Derivatives:** **Fedora** (cutting-edge community version), **CentOS** (formerly the free rebuild of RHEL), **AlmaLinux**, **Rocky Linux**.
        
3. **Slackware**
    - **Philosophy:** One of the oldest distros; prioritizes simplicity, stability, and UNIX-like purity (less automation).
    - **Influence:** Inspired many other distros, though has fewer direct derivatives today.

**Two Types of Computer Interfaces**

1. **Graphical User Interface (GUI)**
    - What it is: The visual, point-and-click interface most people use every day.
    - How it works: You interact with windows, icons, menus, and pointers (WIMP).
    - Examples: Web browsers, photo editors, file managers.
    - Mindset: The interface presents you with **choices** (buttons, menus). You respond by selecting from what's offered. Some say this means **the computer is telling _you_ what to do**.
        
2. **Command Line Interface (CLI)**
    - What it is: A text-based interface where you interact by typing commands.
    - How it works: You type precise instructions at a **command prompt** and press Enter to execute them.
    - Mindset: You express exactly what you want to happen by typing commands. This means **you are telling _the computer_ what to do**.
