

# 🐧 Day 5 — Linux Package Management

Today was **Day 5 of my Linux journey**.

Today I learned about **Linux package management**, installing and removing software, different package managers, and installing a tool from a GitHub repository.

---

# 📦 What is Package Management?

A **package manager** is a tool used to install, update, remove, and manage software packages on Linux.

Instead of manually downloading and installing every dependency, package managers can automatically handle many of them.

For example:

```bash
sudo apt install pidgin
```

---

# 📁 Downloads Directory

When downloading files or repositories manually, I learned that it is useful to keep them organized in a dedicated directory such as:

```bash
cd ~/Downloads
```

This helps keep downloaded files separate from other personal files.

---

# 🐧 Debian-Based Package Management

I learned about **`.deb` packages**.

`.deb` is the package format commonly used by **Debian-based Linux distributions**, such as Ubuntu and Debian.

There are different levels of package management tools.

### Low-level package manager

```text
dpkg
```

`dpkg` works directly with `.deb` packages.

### High-level package managers

```text
apt
aptitude
```

These tools work at a higher level and can manage repositories and dependencies.

---

# 🔧 APT

`apt` is one of the most commonly used package-management tools on Debian-based systems.

### Install a package

```bash
sudo apt install pidgin
```

This installs the `pidgin` package and its required dependencies.

---

### Fix Broken Dependencies

If package installation has dependency problems, I learned:

```bash
sudo apt --fix-broken install
```

This attempts to fix broken package dependencies.

---

### Edit Repository Sources

I learned about:

```bash
sudo apt edit-sources
```

This can be used to edit the configured APT software sources.

When prompted to choose an editor, I practiced selecting an available editor.

---

# 📋 Copying and Viewing Files

I also practiced using commands such as:

```bash
cat
nano
cp
```

### `cat`

Used to display file contents.

```bash
cat filename
```

### `nano`

A simple terminal text editor.

```bash
nano filename
```

### `cp`

Used to copy files.

```bash
cp source destination
```

---

# 🔎 Finding Installed Packages

I learned how to search the list of installed packages.

For example:

```bash
apt list --installed | grep '^nmap'
```

Here:

* `apt list --installed` → lists installed packages
* `|` → sends the output to another command
* `grep` → searches for matching text
* `'^nmap'` → looks for package names beginning with `nmap`

---

# ℹ️ Getting Package Information

### `apt show`

Shows information about a package.

```bash
sudo apt show nmap
```

---

### `apt search`

Searches available packages.

```bash
sudo apt search nmap
```

---

# 🗑️ Removing Packages

I learned that there is a difference between **remove** and **purge**.

### `apt remove`

```bash
sudo apt remove pidgin
```

Removes the package but generally leaves its configuration files behind.

### `apt purge`

```bash
sudo apt purge pidgin
```

Removes the package and its system-wide configuration files.

I also practiced:

```bash
sudo apt list --installed | grep '^pidgin'
```

and:

```bash
sudo apt purge pidgin-data
```

---

# 📊 Levels of Linux Package Management

Today I learned:

```text
        Package Management
               │
       ┌───────┴───────┐
       │               │
     Low Level       High Level
       │               │
     dpkg          ┌───┴────┐
                   │        │
                  apt    aptitude
```

### `dpkg`

Low-level package management tool for Debian packages.

### `apt`

High-level package management tool that works with repositories and dependencies.

### `aptitude`

Another high-level package management tool for Debian-based systems.

---

# 📦 Snap Package Manager

I also learned about **Snap**.

Snap is another package-management and software-distribution system.

Snap packages are commonly distributed through the **Snap Store**.

For example:

```bash
sudo snap install code --classic
```

The `--classic` option is used for snaps that require classic confinement.

---

# 🐙 Installing a Tool From GitHub

Today I also practiced installing a tool from a GitHub repository.

The tool I practiced with was **TurboList3r**.

The basic process I learned was:

```text
GitHub Repository
       ↓
   git clone
       ↓
 Download repository
       ↓
      ls
       ↓
 cd turbolist3r
       ↓
 Install requirements
       ↓
 Run the program
```

---

# 📥 `git clone`

First, I learned how to clone a GitHub repository.

```bash
git clone <repository-url>
```

Then I can check the downloaded files:

```bash
ls
```

Move into the repository:

```bash
cd turbolist3r
```

And check its contents:

```bash
ls
```

---

# 🐍 Installing Python Requirements

The project uses Python dependencies listed in a requirements file.

I learned:

```bash
pip3 install -r requirements.txt
```

This installs the Python packages listed in `requirements.txt`.

> **Note:** The exact filename should match the repository. Many projects use `requirements.txt`.

---

# 🔍 Running TurboList3r

I learned the general command structure:

```bash
python3 turbolist3r.py -d <domain>
```

For example:

```bash
python3 turbolist3r.py -d example.com
```

TurboList3r is a **subdomain enumeration/reconnaissance tool**, so it should only be used against domains you own or are explicitly authorized to test.

---

# 🧠 What I Learned Today

Today I learned:

* What Linux package management is
* `.deb` packages
* `dpkg`
* `apt`
* `aptitude`
* Installing packages
* Removing packages
* Purging packages
* Fixing broken dependencies
* Searching for packages
* Viewing package information
* `grep`
* `cat`
* `nano`
* `cp`
* Snap and the Snap Store
* `git clone`
* Linux software installation from a GitHub repository
* Python `requirements.txt`
* Basic use of TurboList3r

## ⭐ Most Important Lesson

Package managers make installing and managing Linux software much easier.

```text
        Software
           ↓
    Package Manager
           ↓
   Dependencies handled
           ↓
     Software installed
```

I also learned that Linux has **different levels of package management**, from low-level tools like `dpkg` to high-level tools like `apt`.

## 🚀 Day 5 Complete!

Another day of learning Linux completed. 🐧

Today I learned not only how to manage packages, but also how software from a GitHub repository can be downloaded and installed.

**Next → Day 6 🐧**

