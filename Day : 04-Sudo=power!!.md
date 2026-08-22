# 🐧 Day 4 — Users, Groups, sudo & sudoers

Today was **Day 4 of my Linux journey**.

Today I learned about:

* Users
* User IDs (UID)
* Group IDs (GID)
* Passwords
* `sudo`
* `usermod`
* `su`
* `sudoers`
* `visudo`
* `userdel`
* Groups
* `groupadd`

---

# 🔐 Understanding `sudo`

`sudo` allows an authorized user to execute commands with **elevated privileges**, usually as the root user.

For example:

```bash
sudo passwd Ironman
```

Here, `sudo` gives the command the privileges required to change the password for the user `Ironman`.

---

# 👤 Creating Users

I learned about the `adduser` command.

```bash
sudo adduser Ironman
```

This can create a new user and, depending on the Linux distribution, interactively ask for information such as the user's password and details.

---

# 📄 `/etc/passwd`

Linux stores basic information about local user accounts in:

```bash
/etc/passwd
```

I can view it using:

```bash
cat /etc/passwd
```

or:

```bash
sudo cat /etc/passwd
```

A user entry can look like:

```text
Thor:x:1001:1001:Thor:/home/Thor:/bin/bash
```

The fields are separated by `:`.

### Understanding the entry

```text
Thor : x : 1001 : 1001 : Thor : /home/Thor : /bin/bash
```

| Field        | Meaning                                        |
| ------------ | ---------------------------------------------- |
| `Thor`       | Username                                       |
| `x`          | Password is stored separately in `/etc/shadow` |
| `1001`       | UID — User ID                                  |
| `1001`       | GID — Group ID                                 |
| `Thor`       | User information/comment field                 |
| `/home/Thor` | User's home directory                          |
| `/bin/bash`  | User's login shell                             |

### 🔑 What does `x` mean?

The `x` does **not** contain the user's password.

It indicates that the password information is stored separately, normally in:

```bash
/etc/shadow
```

The shadow file is protected because it contains password hashes and other password-related information.

---

# 🆔 UID and GID

I learned that Linux identifies users and groups using numbers.

### UID

**UID = User ID**

Example:

```text
1001
```

identifies a particular user.

### GID

**GID = Group ID**

Example:

```text
1001
```

identifies the user's primary group.

---

# 🔑 Changing a User's Password

I learned the `passwd` command.

For example:

```bash
sudo passwd Ironman
```

This allows an administrator to change the password of the `Ironman` user.

---

# 👨‍💻 `usermod`

The `usermod` command is used to modify an existing user account.

Example:

```bash
sudo usermod [options] username
```

It can be used to modify different properties of a user, depending on the options used.

---

# 🔄 `su`

`su` can be used to switch to another user.

For example:

```bash
su Ironman
```

Or to switch to a root login shell on systems where this is configured:

```bash
su -
```

Unlike `sudo`, `su` changes the current shell to another user's account.

---

# 🛡️ The `sudoers` Configuration

Linux controls who can use `sudo` through its **sudoers configuration**.

The main configuration file is:

```bash
/etc/sudoers
```

I learned that this file controls which users or groups can perform administrative actions using `sudo`.

---

# 📝 `visudo`

Instead of directly editing `/etc/sudoers`, I learned to use:

```bash
sudo visudo
```

`visudo` safely edits and checks the sudoers configuration.

This is important because a syntax error in the sudoers configuration can cause problems with administrative access.

---

# 🚪 Logging Out of a User/Shell

I learned several ways to leave a shell.

### `exit`

```bash
exit
```

### `Ctrl + D`

```text
Ctrl + D
```

`Ctrl + D` sends an end-of-input signal and can exit the current shell.

Depending on the environment, `logout` can also be used to log out from a login shell:

```bash
logout
```

---

# 🗑️ Deleting Users

I learned the `userdel` command.

Example:

```bash
sudo userdel Ironman
```

This deletes the user account.

⚠️ Options such as `-r` can also remove the user's home directory and mail spool, so user deletion should be done carefully.

---

# 👥 Creating Groups

I learned the `groupadd` command.

Example:

```bash
sudo groupadd Avengers
```

This creates a new group called `Avengers`.

Groups are useful for managing permissions for multiple users.

---

# 🦸 Understanding `sudo` With Avengers

To make `sudo` easier to understand, I created an **Avengers: Endgame** example.

Imagine:

* 🦹 **Thanos** = a powerful attacker
* 🧑‍💻 **Iron Man** = a user
* 💎 **Infinity Gauntlet** = powerful administrative privileges
* 🦸 **Avengers** = a group of users
* 👑 **Root** = the highest-privileged account

The Avengers need special power to defeat Thanos.

In Linux, `sudo` is like giving an authorized user temporary access to **powerful administrative abilities**.

For example:

```bash
sudo <command>
```

means:

> "Run this command with elevated privileges if I am authorized to do so."

This helped me understand why `sudo` should be used carefully.

---

# ⚔️ My Thanos Example

I also practiced these concepts using a fun **Avengers/Thanos Linux example**.

📸 **Screenshot coming soon**

I will add my terminal screenshot here showing how I created and managed the `Thanos` user.

---

# 🧠 What I Learned Today

Today I learned:

* `sudo`
* `adduser`
* `/etc/passwd`
* `/etc/shadow`
* UID
* GID
* `passwd`
* `usermod`
* `su`
* `sudoers`
* `visudo`
* `exit`
* `Ctrl + D`
* `logout`
* `userdel`
* `groupadd`
* Users and groups
* Basic Linux privilege management

## ⭐ Most Important Lesson

Linux uses **users, groups, and privileges** to control who can access and modify system resources.

```text
User
  ↓
Group
  ↓
Permissions
  ↓
sudo
  ↓
Administrative privileges
```

## 🚀 Day 4 Complete!

Today I learned how Linux manages users and administrative privileges.

And the best part was understanding `sudo` through my **Avengers vs. Thanos** example. 🦸🐧

**Next → Day 5 🐧**

