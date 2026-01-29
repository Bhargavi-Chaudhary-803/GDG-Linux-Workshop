---
title: "Linux Essentials - Part 1"
author: "GDG Workshop"
theme:
  name: gruvbox-dark
  override:
    footer:
      style: template
      left:
        image: abc.png
      right: "{current_slide} / {total_slides}"
      height: 5
options:
  implicit_slide_ends: true
  command_prefix: "cmd"
---

# Part 1: Introduction & Foundations 🚀
## Understanding Linux & Getting Started

**Duration:** 45 minutes (0:00 - 0:45)

<!-- end_slide -->

## Today's Journey

**What We'll Cover:**
1. The Evolution: From Mainframes to Linux
2. Understanding the Terminology
3. Kernel vs Operating System
4. Why Linux Dominates
5. GNU & The Free Software Movement

<!-- end_slide -->

# The Beginning 🕰️
## How It All Started

<!-- end_slide -->

## The 1960s: Birth of Computing

**The Mainframe Era**
* Computers were room-sized machines
* Cost millions of dollars
* Only universities and corporations had access
* No personal computers existed
* Operated using punch cards!

**The Problem:** Multiple users needed to share ONE computer.

<!-- end_slide -->

## 1969: UNIX is Born 🌟

**At Bell Labs (AT&T)**
* Ken Thompson & Dennis Ritchie
* Created for the PDP-7 minicomputer
* Revolutionary idea: Time-sharing system
* Written in C language (portable!)

**UNIX Philosophy:**
> "Do one thing and do it well"

<!-- end_slide -->

## UNIX's Key Innovations

**What Made UNIX Special:**
1. **Multi-user:** Multiple people could use it simultaneously
2. **Multi-tasking:** Run multiple programs at once
3. **Portable:** Could run on different hardware
4. **Hierarchical File System:** The `/` tree structure
5. **Everything is a file:** Even devices!

<!-- end_slide -->

## The Problem with UNIX

**The Catch:**
* UNIX was **proprietary**
* Extremely **expensive** (tens of thousands of dollars)
* Source code was **closed**
* Required expensive hardware
* Licensing restrictions were strict

Universities wanted to teach it, but couldn't afford it!

<!-- end_slide -->

## 1983: The GNU Project 🦬

**Richard Stallman's Vision**
* Started the Free Software Foundation
* Goal: Create a **free** UNIX-like OS
* GNU = "GNU's Not Unix" (recursive acronym!)

**The Problem:** They built all the tools but... no kernel!

**GNU Created:**
* GCC (compiler)
* bash (shell)
* Core utilities (ls, cp, mv, etc.)

<!-- end_slide -->

## 1987: MINIX Enters

**Andrew Tanenbaum** created MINIX
* Teaching tool for operating systems
* UNIX-like, but simplified
* Source code available (for education)
* Restrictive licensing

A Finnish student named **Linus Torvalds** was using it...

<!-- end_slide -->

## 1991: Linux is Born! 🐧

**August 25, 1991 - Linus Torvalds posts:**

> "I'm doing a (free) operating system (just a hobby, won't be big and professional like GNU)"

**What Linus Created:**
* The **kernel** - the core of the OS
* Released under GPL (completely free)
* Invited collaboration from anyone
* Combined with GNU tools = Complete OS!

<!-- end_slide -->

## Why "Linux" Won 🏆

**The Perfect Storm:**
1. **Free & Open Source:** Anyone could use, modify, distribute
2. **GNU Tools Ready:** Complete ecosystem existed
3. **Internet Timing:** Could collaborate globally
4. **Community Driven:** Thousands contributed
5. **Unix Philosophy:** Well-tested design principles

<!-- end_slide -->

# Understanding the Terms 📚
## CLI, Shell, Terminal, GUI

<!-- end_slide -->

## GUI vs CLI

**GUI (Graphical User Interface)**
* Windows, icons, buttons, mouse
* What you're used to: Windows, macOS
* Easy to learn, visual feedback
* Limited automation capabilities

**CLI (Command Line Interface)**
* Text-based interaction
* Type commands, get text output
* Steeper learning curve
* Powerful automation & scripting

<!-- end_slide -->

## What is a Terminal? 🖥️

**Historical Context:**
* Originally a physical device
* Connected to mainframe computers
* Had a keyboard and display
* Multiple terminals → One computer

**Today:**
* **Terminal Emulator** = Software that mimics old terminals
* Examples: GNOME Terminal, iTerm2, Windows Terminal
* Just a window that runs a shell!

<!-- end_slide -->

## What is a Shell? 🐚

**The Shell is Your Interpreter**
* Takes your commands (text)
* Translates them for the kernel
* Returns the output to you

**Think of it as:**
* The shell is the **translator**
* You speak human → Shell speaks machine

<!-- end_slide -->

## Popular Shells

| Shell | Name | Notes |
| :--- | :--- | :--- |
| `sh` | Bourne Shell | The original (1979) |
| `bash` | Bourne Again Shell | Most common default |
| `zsh` | Z Shell | Modern, feature-rich (macOS default) |
| `fish` | Friendly Interactive Shell | Beginner-friendly |

> [!TIP]
> We'll use **bash** today as it's the most universal!

<!-- end_slide -->

## The Relationship 🔗

```text
┌─────────────────────────────────┐
│      Terminal Emulator          │  ← The window you see
│  ┌───────────────────────────┐  │
│  │        Shell (bash)       │  │  ← Interprets commands
│  │  ┌─────────────────────┐  │  │
│  │  │   Your Command      │  │  │  ← What you type
│  │  └─────────────────────┘  │  │
│  │           ↓                │  │
│  │  ┌─────────────────────┐  │  │
│  │  │    Kernel           │  │  │  ← Executes on hardware
│  │  └─────────────────────┘  │  │
│  └───────────────────────────┘  │
└─────────────────────────────────┘
```

<!-- end_slide -->

## CLI in Action

**Example Workflow:**

1. You open **Terminal** (the app)
2. **Shell** (bash) starts and waits
3. You type: `ls -la`
4. **Shell** interprets this
5. **Kernel** executes the command
6. Output returns through Shell to Terminal
7. You see the result!

<!-- end_slide -->

# Kernel vs Operating System 🧠
## What's the Difference?

<!-- end_slide -->

## What is a Kernel? ⚙️

**The Kernel is the CORE**
* Sits between hardware and software
* Manages system resources
* Direct communication with hardware
* Most privileged software component

**Key Responsibilities:**
1. Process management
2. Memory management
3. Device drivers
4. System calls
5. Security & permissions

<!-- end_slide -->

## Kernel's Job Explained

**Think of the Kernel as a Restaurant Manager:**

* **Hardware** = Kitchen (CPU, RAM, Disk)
* **Applications** = Customers (programs)
* **Kernel** = Manager coordinating everything

**Example:**
When you open a browser:
* Kernel allocates RAM
* Kernel schedules CPU time
* Kernel handles network access
* Kernel manages disk I/O

<!-- end_slide -->

## What is an Operating System? 💿

**The OS is EVERYTHING:**
* Kernel + System Software + Utilities
* User interface (GUI or CLI)
* System libraries
* Configuration tools
* Application frameworks

**Formula:**
```
Operating System = Kernel + Everything Else
```

<!-- end_slide -->

## Linux: The Kernel 🐧

**Technically Speaking:**
* "Linux" is JUST the kernel
* Created by Linus Torvalds
* Manages hardware resources
* ~30 million lines of code!

**But everyone says "Linux OS" because:**
* Linux kernel + GNU tools = Complete system
* Common shorthand
* "GNU/Linux" is technically correct but rarely used

<!-- end_slide -->

## Kernel Architecture

```text
┌────────────────────────────────────┐
│      User Space (Applications)     │
├────────────────────────────────────┤
│         System Call Interface      │
├────────────────────────────────────┤
│                                    │
│         Linux Kernel               │
│  ┌──────────┬──────────┬────────┐ │
│  │ Process  │  Memory  │  File  │ │
│  │   Mgmt   │   Mgmt   │ System │ │
│  ├──────────┼──────────┼────────┤ │
│  │      Device Drivers            │ │
│  └────────────────────────────────┘ │
├────────────────────────────────────┤
│    Hardware (CPU, RAM, Disk, etc)  │
└────────────────────────────────────┘
```

<!-- end_slide -->

## System Calls: The Bridge 🌉

**How Programs Talk to Kernel:**
* Applications can't directly access hardware
* They make "system calls" to the kernel
* Kernel validates and executes safely

**Example: Opening a File**
```c
// Your program does this:
int fd = open("/home/user/data.txt", O_RDONLY);

// Behind the scenes:
// 1. System call to kernel
// 2. Kernel checks permissions
// 3. Kernel accesses disk
// 4. Returns file descriptor
```

<!-- end_slide -->

## Types of Kernels

**Monolithic (Linux)**
* Everything in one big kernel
* Drivers, file systems, networking - all included
* Fast but large
* Linux approach

**Microkernel**
* Minimal core functionality
* Most services run in user space
* More stable, slower
* Example: MINIX, QNX

**Hybrid**
* Mix of both approaches
* Example: Windows NT, macOS

<!-- end_slide -->

# Why Linux is the Best 🏆
## (For Most Things!)

<!-- end_slide -->

## Linux Dominates The World

**Where Linux Runs:**
* 96.3% of top 1 million web servers
* 100% of top 500 supercomputers
* Every Android phone (Linux kernel)
* Billions of IoT devices
* Most cloud infrastructure (AWS, Google Cloud, Azure)
* Mars rovers and ISS systems
* Your smart TV, router, car infotainment...

<!-- end_slide -->

## Why Linux Won

**1. It's Free (Freedom + Price)**
* No licensing costs
* Can modify source code
* Redistribute freely
* No vendor lock-in

**2. Security**
* Open source = Many eyes reviewing
* Fast security patches
* Granular permission system
* Less malware targets it

<!-- end_slide -->

## Why Linux Won (cont.)

**3. Stability & Performance**
* Can run for years without reboot
* Efficient resource usage
* Scales from smartwatch to supercomputer
* No forced updates or restarts

**4. Customization**
* Change EVERYTHING
* Choose your desktop environment
* Mix and match components
* Build your own distribution

<!-- end_slide -->

## Why Linux Won (cont.)

**5. Developer Heaven**
* Best programming tools included
* Package managers for easy installs
* Native Docker support
* Most languages install easily
* Remote access built-in (SSH)

**6. Community**
* Massive global community
* Free support forums
* Extensive documentation
* Thousands of contributors

<!-- end_slide -->

## The Power of Open Source 💪

**Linux Development Model:**
* Anyone can contribute code
* Reviewed by maintainers
* Best solutions win
* Meritocracy-based

**The Numbers:**
* 30+ million lines of code
* 20,000+ contributors
* 15,000+ companies involved
* New version every 9-10 weeks

<!-- end_slide -->

## Linux vs Others: Quick Compare

| Feature | Linux | Windows | macOS |
| :--- | :--- | :--- | :--- |
| Cost | Free | $100+ | $1000+ (with Mac) |
| Source | Open | Closed | Closed |
| Customization | Total | Limited | Limited |
| Privacy | Excellent | Concerns | Concerns |
| Servers | 96% | 4% | <1% |
| Updates | Your choice | Forced | Frequent |

<!-- end_slide -->

## Real World Impact 🌍

**Financial Systems:**
* Stock exchanges run Linux
* Banking infrastructure
* Payment processing

**Entertainment:**
* Netflix servers
* Disney/Pixar render farms
* Spotify, YouTube infrastructure

**Science:**
* CERN particle accelerators
* Human Genome Project
* Climate modeling systems

<!-- end_slide -->

# GNU & The Movement 🦬
## More Than Just Software

<!-- end_slide -->

## What is GNU?

**GNU = GNU's Not Unix**
* Started in 1983 by Richard Stallman
* Goal: Create completely free UNIX replacement
* Developed all the essential tools

**The GNU Components:**
* bash (shell)
* GCC (compiler)
* coreutils (ls, cp, mv, cat, etc.)
* glibc (C library)
* GNU Make, grep, sed, awk...

<!-- end_slide -->

## The Four Freedoms

**Free Software Definition:**

0. **Freedom to RUN** the program for any purpose
1. **Freedom to STUDY** how it works (source code)
2. **Freedom to REDISTRIBUTE** copies
3. **Freedom to IMPROVE** and share improvements

**"Free as in freedom, not just free beer"**

<!-- end_slide -->

## GNU + Linux = Complete OS

**Before 1991:**
* GNU had: tools, compiler, shell, utilities
* GNU needed: a kernel (GNU Hurd was incomplete)

**After 1991:**
* Linus released Linux kernel
* Linux needed: all the userspace tools
* Perfect match! 🤝

**Result:**
* Linux kernel + GNU tools = GNU/Linux system
* Most people just say "Linux"

<!-- end_slide -->

## GPL: The License 📜

**GNU General Public License**
* Copyleft license (not copyright!)
* You CAN: use, modify, distribute
* You MUST: share source code if you distribute
* Modifications must also be GPL

**The Viral Effect:**
* Any code linking to GPL code becomes GPL
* Prevents "embrace and extend"
* Ensures freedom propagates

<!-- end_slide -->

## Open Source vs Free Software

**Free Software (FSF/GNU)**
* Emphasis on freedom and ethics
* Must follow the four freedoms
* GPL licensing preferred

**Open Source (OSI)**
* Emphasis on practical benefits
* More permissive licenses okay
* Business-friendly approach

**Linux:** Uses GPL but community includes both philosophies

<!-- end_slide -->

## Why GNU Matters

**Without GNU:**
* Linux kernel would be useless alone
* Need compiler to build more software
* Need shell to interact with system
* Need core utilities for basic operations

**GNU Provided:**
* The entire userland
* Development toolchain
* Philosophy of freedom
* Community model

<!-- end_slide -->

## The Impact Today

**GNU Tools Run Everywhere:**
* Every Linux distribution
* macOS (many GNU tools)
* Android (some GNU components)
* Embedded systems
* Your router, TV, car...

**The Philosophy Lives:**
* GitHub, GitLab host millions of open projects
* Modern languages (Python, Go, Rust) are open
* Open source is now the norm for infrastructure

<!-- end_slide -->

## Linux Distributions Explained 🎨

**A Distribution ("Distro") is:**
* Linux kernel
* + GNU tools
* + Package manager
* + Desktop environment (optional)
* + Pre-configured settings
* + Their own philosophy

**Popular Families:**
* Debian → Ubuntu → Mint, Pop!_OS
* Red Hat → Fedora → CentOS
* Arch → Manjaro, EndeavourOS

<!-- end_slide -->

## Choosing a Distribution

**For Beginners:**
* **Ubuntu** - Most popular, massive support
* **Linux Mint** - Very Windows-like
* **Pop!_OS** - Great for gaming

**For Servers:**
* **Ubuntu Server** / **Debian**
* **Red Hat Enterprise Linux**
* **Rocky Linux** / **AlmaLinux**

**For Advanced Users:**
* **Arch Linux** - Build it yourself
* **Gentoo** - Compile everything!

<!-- end_slide -->

## Package Managers 📦

**What They Do:**
* Install software with one command
* Handle dependencies automatically
* Keep everything updated
* Remove software cleanly

**Major Package Managers:**
* `apt` (Debian, Ubuntu)
* `dnf` / `yum` (Fedora, RHEL)
* `pacman` (Arch)
* `zypper` (openSUSE)

<!-- end_slide -->

## Desktop Environments 🖼️

**Linux Lets You Choose Your Interface!**

**Popular Options:**
* **GNOME** - Modern, macOS-like
* **KDE Plasma** - Feature-rich, Windows-like
* **XFCE** - Lightweight, fast
* **Cinnamon** - Traditional, elegant
* **i3/sway** - Tiling, keyboard-driven

You can switch anytime!

<!-- end_slide -->

# Quick Recap 📝
## What We Learned

<!-- end_slide -->

## The Journey So Far

**History:**
* UNIX (1969) → Expensive, proprietary
* GNU (1983) → Free tools, no kernel
* Linux (1991) → Free kernel
* GNU + Linux = Complete free OS

**Terminology:**
* **Terminal:** The window/app
* **Shell:** The command interpreter
* **CLI:** Text-based interface
* **GUI:** Graphical interface

<!-- end_slide -->

## The Journey So Far (cont.)

**Technical Understanding:**
* **Kernel:** Core that manages hardware
* **OS:** Kernel + all the software
* **Linux:** Is the kernel
* **GNU/Linux:** The complete system

**Why Linux:**
* Free & open source
* Secure & stable
* Highly customizable
* Runs the world's infrastructure
* Amazing community

<!-- end_slide -->

## Looking Ahead 👀

**Next Up:**
* Exploring the file system
* Basic commands and navigation
* Understanding permissions
* Shell scripting basics

**Remember:**
* Linux mastery takes time
* Practice regularly
* Don't be afraid to break things (in VM!)
* The community is here to help

<!-- end_slide -->

# Questions? 🤔

**Resources to Continue Learning:**
* Linux Journey: linuxjourney.com
* OverTheWire (wargames): overthewire.org
* /r/linux4noobs on Reddit
* Linux Documentation Project
* Man pages (`man command`)

<!-- end_slide -->

# Let's Get Hands-On! 🚀
## Ready to Dive Into the Terminal?

**Next Section:** Navigation & File System Basics

<!-- end_slide -->
