
# 🐧 Day 7 — Linux Process Management

Today I learned about **Linux processes and process management**.

A **process** is a running instance of a program. Every process has a unique **PID (Process ID)**.

## 🔍 Finding Processes

### `ps`

The `ps` command is used to display running processes.

```bash
ps -u username
```

To find a specific process:

```bash
ps -u username | grep firefox
```

* `ps` → displays processes
* `-u username` → shows processes belonging to a particular user
* `grep firefox` → filters the output and shows lines containing `firefox`

**Grep** stands for **Global Regular Expression Print**.

### `pgrep`

`pgrep` can directly find the PID of a process by its name.

```bash
pgrep firefox
```

Example output:

```text
2736
2810
```

If multiple Firefox processes are running, `pgrep` can return multiple PIDs.

## 🛑 Killing a Process

The `kill` command sends a signal to a process.

```bash
kill 2736
```

By default, `kill` sends **SIGTERM (15)**, which politely asks the process to terminate.

If the process does not terminate normally, we can forcefully kill it:

```bash
kill -9 2736
```

`-9` sends **SIGKILL**, which forcefully terminates the process.

It is better to try:

```bash
kill 2736
```

before using:

```bash
kill -9 2736
```

## 📊 Monitoring Processes

### `top`

```bash
top
```

`top` displays currently running processes and system resource usage such as:

* PID
* CPU usage
* Memory usage
* User
* Process state

Press `q` to quit `top`.

### `htop`

```bash
htop
```

`htop` provides similar information to `top`, but with a more interactive and user-friendly interface.

## 🖥️ Foreground and Background Processes

Linux processes can run in the **foreground** or **background**.

### Foreground Process

A foreground process runs directly in the terminal and occupies the terminal until it finishes.

Example:

```bash
ping google.com
```

To interrupt a foreground process:

```text
Ctrl + C
```

`Ctrl + C` sends **SIGINT** and normally terminates the foreground process.

### `Ctrl + Z`

`Ctrl + Z` does **not normally kill** a process.

It **suspends** the foreground process and puts it into the shell's job list.

Example:

```bash
ping google.com
```

Press:

```text
Ctrl + Z
```

The process becomes stopped/suspended.

## 📋 `jobs`

The `jobs` command shows jobs managed by the current shell.

```bash
jobs
```

Example:

```text
[1]+  Stopped    ping google.com
```

Here `[1]` is the **job number**, not the PID.

* PID → Process ID
* `%1` → Job number 1

## ⬆️ `fg`

The `fg` command brings a background or suspended job to the foreground.

```bash
fg %1
```

After bringing it to the foreground, we can press:

```text
Ctrl + C
```

to terminate it.

The general process is:

```bash
ping google.com
```

Press:

```text
Ctrl + Z
```

Then:

```bash
jobs
```

Then:

```bash
fg %1
```

Then:

```text
Ctrl + C
```

## ⬇️ Background Processes

A command can be started directly in the background using `&`.

```bash
ping google.com &
```

The terminal remains available while the process runs in the background.

We can check background jobs using:

```bash
jobs
```

We can bring a job back to the foreground using:

```bash
fg %1
```

We can also continue a stopped job in the background using:

```bash
bg %1
```

## 🎯 `pkill`

The `pkill` command can send a signal to processes based on their name.

For example:

```bash
pkill ping
```

This terminates processes matching the name `ping` using the default termination signal.

To forcefully kill matching processes:

```bash
pkill -9 ping
```

`-9` sends **SIGKILL**.

Use force-killing carefully because the process does not get an opportunity to shut down gracefully.

## 🧠 Important Commands Learned

| Command                          | Purpose                           |
| -------------------------------- | --------------------------------- |
| `ps`                             | Display processes                 |
| `ps -u username`                 | Display a user's processes        |
| `grep`                           | Search/filter text                |
| `ps -u username \| grep firefox` | Find Firefox processes            |
| `pgrep firefox`                  | Find Firefox PID(s)               |
| `kill PID`                       | Ask a process to terminate        |
| `kill -9 PID`                    | Forcefully kill a process         |
| `top`                            | Monitor running processes         |
| `htop`                           | Interactive process monitor       |
| `jobs`                           | Show shell jobs                   |
| `fg %1`                          | Bring job 1 to foreground         |
| `bg %1`                          | Continue job 1 in background      |
| `pkill ping`                     | Terminate processes by name       |
| `pkill -9 ping`                  | Forcefully kill processes by name |

## ⭐ Key Things to Remember

```text
Ctrl + C  → Interrupt/terminate the foreground process
Ctrl + Z  → Suspend the foreground process
fg %1     → Bring job 1 to the foreground
bg %1     → Continue job 1 in the background
kill PID  → Send a termination signal to a process
kill -9 PID → Forcefully kill a process
pkill name → Kill processes by name
jobs      → Show shell jobs
```

### 🎓 Day 7 Summary

Today I learned how to **find, monitor, stop, suspend, resume, and terminate Linux processes** using commands such as `ps`, `grep`, `pgrep`, `kill`, `top`, `htop`, `jobs`, `fg`, `bg`, and `pkill`.

The most important concepts I learned are the difference between a **PID and a job number**, and the difference between **Ctrl+C (interrupt)** and **Ctrl+Z (suspend)**.
