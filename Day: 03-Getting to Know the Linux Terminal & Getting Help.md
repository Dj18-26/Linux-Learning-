# 🐧 Day 3 — Getting to Know the Linux Terminal & Getting Help

Today was **Day 3 of my Linux journey**.

One important thing I learned today is:

> **When you get stuck in Linux, you can get help!**

Linux has a huge number of commands, and remembering everything is difficult. Instead of trying to memorize every command, I learned how to **find information and understand commands using built-in help tools**.

---

# 💻 Getting to Know the Linux Terminal

The command-line environment can be described using several related terms:

* **Terminal** — The application/interface where we interact with the command line.
* **Shell** — The program that interprets the commands we type.
* **Bash** — A popular Unix shell and the default shell on many Linux systems.
* **Console** — A general term for a command-line interface.

So, these words are related, but they don't all mean exactly the same thing.

---

# 💲 Linux Prompt Symbols

I learned that the prompt can give us information about the current user.

### `$`

Usually indicates a **regular user**.

```text
$
```

### `#`

Usually indicates the **root user**.

```text
#
```

For example:

```text
user@linux:~$
```

A root shell may look like:

```text
root@linux:~#
```

⚠️ Be careful when working as root because commands can make system-wide changes.

---

# 🔎 Commands I Learned

Today I explored several commands that help me understand the Linux system.

### `ps`

Shows information about currently running processes.

```bash
ps
```

---

### `id`

Shows user and group identity information.

```bash
id
```

---

### `hostname`

Displays or sets the system's hostname.

```bash
hostname
```

---

### `uname`

Displays information about the Linux system/kernel.

```bash
uname
```

A useful option is:

```bash
uname -a
```

---

### `ifconfig`

Displays network interface information.

```bash
ifconfig
```

⚠️ `ifconfig` is considered a legacy command on many modern Linux systems. The `ip` command is generally preferred.

---

### `ip`

Used to view and manage network interfaces, addresses, routes, and more.

```bash
ip addr
```

---

### `netstat`

Can display network connections, routing information, and listening ports.

```bash
netstat
```

⚠️ On many modern Linux distributions, `ss` is preferred over `netstat`.

---

### `ss`

Displays socket and network connection information.

```bash
ss
```

For example:

```bash
ss -tuln
```

---

### `env`

Displays environment variables.

```bash
env
```

---

### `lsblk`

Lists information about block devices such as disks and partitions.

```bash
lsblk
```

---

### `lsusb`

Displays USB devices connected to the system.

```bash
lsusb
```

---

### `lsof`

Lists open files and can help identify which processes are using files, devices, or network connections.

```bash
lsof
```

---

# 🆘 Getting Help in Linux

This was one of the most important things I learned today.

There are too many Linux commands and options to memorize everything.

Instead, **Linux provides built-in documentation and help tools.**

---

## 📖 `man` — Manual Pages

The `man` command displays the manual page for a command.

For example:

```bash
man uname
```

```bash
man ls
```

```bash
man ip
```

This gives detailed information about the command, including its options and usage.

To exit a `man` page:

```text
q
```

---

# 💡 `--help`

Many commands provide a shorter help message using `--help`.

For example:

```bash
uname --help
```

This is useful when I want a quick overview instead of reading the complete manual.

---

# 🔍 `apropos`

The `apropos` command helps find commands related to a keyword by searching manual-page descriptions.

For example:

```bash
apropos usb
```

Or:

```bash
apropos compress
```

This is useful when I **know what I want to do but don't know which command to use**.

---

# 🧠 What I Learned Today

Today I learned:

* What the Linux terminal is
* The difference between terminal, shell, Bash, and console
* `$` usually represents a regular-user prompt
* `#` usually represents a root prompt
* `ps`
* `id`
* `hostname`
* `uname`
* `ifconfig`
* `ip`
* `netstat`
* `ss`
* `env`
* `lsblk`
* `lsusb`
* `lsof`
* `man`
* `--help`
* `apropos`

## ⭐ Most Important Lesson

I don't need to memorize every Linux command.

I need to learn **how to find the information I need**.

```text
Don't know the command?
        ↓
Use man
        ↓
Need quick help?
        ↓
Use --help
        ↓
Don't know which command to use?
        ↓
Use apropos
```

## 🚀 Day 3 Complete!

Linux has thousands of commands and options, so getting stuck is normal.

The important thing is knowing **how to find the answer**.

**Next → Day 4 🐧**
