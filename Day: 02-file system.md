Great progress. For **Day 2**, I'd recommend documenting it in the same style as Day 1, while correcting a few command/path details so your notes stay technically accurate.

# 🐧 Day 2 — Linux File System & Basic Commands

Today I continued my Linux learning journey and learned about the **Linux file system**, important directories, and several useful commands.

## 📂 Linux File System

Linux has a hierarchical file system. The top-level directory is:

```bash
/
```

Important directories I learned about:

| Directory | Purpose                                           |
| --------- | ------------------------------------------------- |
| `/bin`    | Essential user commands                           |
| `/sbin`   | Essential system/administrative commands          |
| `/usr`    | User applications, utilities, and other resources |
| `/boot`   | Files required for booting Linux                  |
| `/var`    | Variable data such as logs and caches             |
| `/tmp`    | Temporary files                                   |
| `/lib`    | Essential shared libraries                        |
| `/home`   | Home directories of regular users                 |
| `/root`   | Home directory of the root user                   |
| `/dev`    | Device files                                      |
| `/etc`    | System configuration files                        |

---

## 👤 User Commands

### `whoami`

Shows the username of the currently logged-in user.

```bash
whoami
```

---

## 🧹 Clearing the Terminal

### `clear`

Clears the terminal screen.

```bash
clear
```

### `Ctrl + L`

Another shortcut for clearing the visible terminal screen.

```text
Ctrl + L
```

---

# 📁 `/bin`

The `/bin` directory contains essential commands that are available to users.

I learned how to navigate into it:

```bash
cd /bin
```

Some commands I practiced:

### `cat`

Displays the contents of a file.

```bash
cat filename
```

### `cp`

Copies files or directories.

```bash
cp source destination
```

### `rm`

Removes files.

```bash
rm filename
```

⚠️ Be careful with `rm` because deleted files may not be recoverable through a normal recycle bin.

---

# 🔐 `sudo`

`sudo` allows an authorized user to run a command with elevated privileges.

Example:

```bash
sudo cat /etc/network/interfaces
```

It may ask for the user's password.

---

# 📁 `/sbin`

`/sbin` contains many system administration commands.

I learned about:

```bash
adduser
```

For example:

```bash
sudo adduser username
```

This can be used to create a new user on many Linux distributions.

---

# 📦 `/usr`

Another important directory is:

```bash
/usr
```

Some important subdirectories include:

```text
/usr/bin
/usr/sbin
```

On many modern Linux systems, `/bin` and `/sbin` may be symbolic links to:

```text
/usr/bin
/usr/sbin
```

So I learned that these paths can be connected through the modern Linux filesystem layout.

---

## 🔎 `which`

The `which` command shows where an executable command is located.

Example:

```bash
which cat
```

It may return something like:

```text
/usr/bin/cat
```

This helps me understand **where Linux finds commands**.

---

# 💽 `/dev`

The `/dev` directory contains special files representing devices.

For example, a storage device may appear as:

```text
/dev/vda
```

I practiced:

```bash
sudo cat /dev/vda
```

⚠️ **Important:** Reading a block device directly with `cat` is generally not useful and can produce binary/garbled output. It can also cause a lot of data to be read from the device.

To stop a running command, I learned:

```text
Ctrl + C
```

`Ctrl + C` sends an interrupt to the currently running foreground process.

---

# ⚙️ `/etc`

The `/etc` directory contains system-wide configuration files.

I explored the network configuration area:

```bash
cd /etc/network
```

Then:

```bash
sudo cat interfaces
```

This can display the contents of the `interfaces` configuration file on systems that use that networking configuration method.

---

# 🧠 What I Learned Today

Today I learned about:

* Linux file system hierarchy
* `/bin`
* `/sbin`
* `/usr`
* `/boot`
* `/var`
* `/tmp`
* `/lib`
* `/home`
* `/root`
* `/dev`
* `/etc`
* `whoami`
* `clear`
* `Ctrl + L`
* `cat`
* `cp`
* `sudo`
* `rm`
* `adduser`
* `which`
* `Ctrl + C`

## 🚀 Day 2 Complete!

I'm continuing to build my Linux fundamentals one day at a time.

**Next → Day 3 🐧**
