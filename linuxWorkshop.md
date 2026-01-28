---
title: "Linux Essentials"
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

Linux Essentials 🐧
---

**Agenda**
1. History & Distros
2. Filesystem & Navigation
3. Permissions
4. Piping & Scripting

<!-- end_slide -->

## Unix vs. Linux

**Unix (The Grandparent)**
* Born in 1969 at Bell Labs.
* Proprietary & Expensive.
* Philosophy: "Do one thing and do it well."

## Enter Linux

**Linux (The Kernel)**
* Created by Linus Torvalds (1991).
* Free and Open Source (GPL).
* **Linux is the kernel.** The tools are GNU.

![Tux](tux.png)

<!-- end_slide -->

> [!TIP]
> **Android** runs on the Linux Kernel, but it doesn't use the standard GNU tools we are learning today.
> &nbsp;

## WSL Setup

For the Windows users in the room today.

**WSL 2 (Windows Subsystem for Linux)**
Allows running Linux binaries natively on Windows.

```powershell 
# Open PowerShell as Administrator
wsl --install
```

> [!CAUTION]
> You must **restart your computer** after the installation finishes for the changes to take effect.
> &nbsp;

<!-- end_slide -->

## Navigation

The terminal is a text-based map.

| Command | Name | Description |
| :--- | :--- | :--- |
| `pwd` | Print Working Directory | Where am I? |
| `ls` | List | What is here? |
| `cd` | Change Directory | Go somewhere else. |

<!-- end_slide -->

**Live Demo:**

```bash +exec
# Let's see where presenterm is running from!
echo "I am currently at:"
pwd
echo "Files here:"
ls -F
```

<!-- end_slide -->

## The Filesystem Tree

Unlike Windows (`C:\`), Linux has a **Single Root**.

```text {1|2|3|4|5|6|7}
/ (Root)
├── bin/      # Binaries (ls, cp)
├── etc/      # Config files
├── home/     # User data (~)
│   └── gdg/
├── var/      # Logs/Variable data
└── tmp/      # Temporary files
```
<!-- end_slide -->

**Key Commands (CRUD):**

```bash
mkdir folder   # Create
touch file.txt # Create File
cp src dst     # Copy
mv src dst     # Move/Rename
rm file        # Delete
```

<!-- end_slide -->

## Permissions

Who is allowed to do what?

<span style="color: cyan">drwxr-xr--</span>

**The Breakdown:**

1.  <span style="color: blue">d</span>: Directory (or `-` for file)
2.  <span style="color: green">r</span><span style="color: yellow">w</span><span style="color: red">x</span> (Owner): Read, Write, Exec
3.  <span style="color: green">r</span>-<span style="color: red">x</span> (Group): Read, No Write, Exec
4.  <span style="color: green">r</span>-- (Others): Read Only

**Octal Math:**

* **R**ead = 4
* **W**rite = 2
* e**X**ecute = 1

*Example:* `chmod 755`
(Owner: 4+2+1=7)

<!-- end_slide -->

## Altering Permissions

**chmod** (Change Mode) & **chown** (Change Owner).

```bash {1-2|4-5} +line_numbers
# Give the owner execution rights
chmod u+x script.sh

# Give Everyone (4+2+1) everything (Dangerous!)
chmod 777 secret_key.pem
```

> [!WARNING]
> Never use `chmod 777` on production servers. It is a massive security risk.
> &nbsp;

<!-- end_slide -->

## Input, Output & Piping

**Streams:**
* `stdin` (0): Keyboard
* `stdout` (1): Screen
* `stderr` (2): Error

**The Pipe `|`**
Takes the output of the left and pushes it to the right.

```bash +exec
# List files, but filter for 'md' extension
ls -la | grep ".md"
```

<!-- end_slide -->

## Shell Scripting

Let's automate a "Hello World".

**The Shebang (`#!`)** tells the system which interpreter to use.

```bash +exec +line_numbers
#!/bin/bash

# Define a variable
EVENT="GDG Workshop"

echo "Running script for $EVENT..."

# A simple loop
for i in {1..3}
do
    echo "Count: $i"
done
```
<!-- end_slide -->


## Process Management (Hands On)

We are going to purposefully freeze the terminal.

1.  Run the command below.
2.  Press <span style="color: yellow">Ctrl + Z</span> to suspend it.
3.  Type `bg` to push it to the background.
4.  Type `fg` to bring it back.

```bash
sleep 1000
```

<!-- end_slide -->

**Other Tools:**
* `top` / `htop`: Task Manager.
* `ps aux`: Snapshot of processes.
* `kill [PID]`: Stop a process.

<!-- end_slide -->

# Thank You! 

**Workshop Challenge:**
Create a script that:
 1. Makes a directory named `workshop`
 2. Goes into it. 
 3. Creates a file named `done.txt`.
