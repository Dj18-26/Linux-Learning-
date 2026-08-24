
# 🔎 Additional Practice — GitHub Repository & Subfinder

This was an **extra/random part of my Linux learning path**, not a new learning day.

While exploring Linux tools, I found a repository on **GitHub** called **Subfinder**.

I learned that when a project is available on GitHub, I can clone the repository to my Linux system using:

```bash
git clone <repository-link>
```

After cloning the repository, I can check the files:

```bash
ls
```

Then move into the repository:

```bash
cd subfinder
```

And check its contents:

```bash
ls
```

## 🌐 Using Subfinder with a Domain

I learned that Subfinder can be used for **subdomain enumeration**.

The basic command is:

```bash
subfinder -d example.com
```

Here:

* `subfinder` → the tool
* `-d` → specifies the target domain
* `example.com` → the domain being tested

For example:

```bash
subfinder -d example.com
```

This helps discover subdomains associated with the domain.

> ⚠️ I will only use reconnaissance tools such as Subfinder on domains I own or have explicit permission to test.

## 🧠 What I Learned

```text
Find a repository on GitHub
        ↓
Copy the repository link
        ↓
git clone <repository-link>
        ↓
ls
        ↓
cd subfinder
        ↓
Install/setup the tool
        ↓
Use the tool with a domain
        ↓
subfinder -d example.com
```

This was an **additional practical exercise during my Day 5 learning**, not Day 6.
