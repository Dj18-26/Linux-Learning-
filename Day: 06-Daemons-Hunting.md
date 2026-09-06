
🔹 Daemon Hunting

## 1. What is a Daemon?

A daemon is a background process that runs in the system and provides a service.

In simple words:

Daemon → Background Process → Service

Examples:
- Networking
- Printing
- SSH (sshd)
- NTP (Network Time Protocol)

Daemons can run automatically in the background without direct user interaction.


## 2. Checking Running Processes

The `ps` command is used to view information about running processes.

Command:

ps aux

Meaning of `ps aux`:

- `a` → Shows processes for all users
- `u` → Shows processes in a user-oriented format, including CPU and memory usage
- `x` → Includes processes without a controlling terminal, such as background services and daemons.


## 3. Finding a Specific Process

We can use `grep` with `ps aux` to search for a specific process.

Command:

ps aux | grep ssh

This searches for processes related to SSH.

Another example:

ps aux | grep ntp

NTP stands for Network Time Protocol.


## 4. systemd

`systemd` is a system and service manager used by many modern Linux distributions.

It manages:

- System initialization
- Background services
- Daemons
- Mounting filesystems
- Starting required services

Simplified boot process:

Boot → Kernel → systemd → Services / Daemons

After the kernel starts, systemd takes control and manages the system services and daemons.


## 5. systemctl

`systemctl` is used to control and manage services handled by `systemd`.


### Start a Service

Command:

sudo systemctl start sshd

This starts the SSH service.


### Stop a Service

Command:

sudo systemctl stop sshd

This stops the SSH service.


### Restart a Service

Command:

sudo systemctl restart sshd

This stops and starts the service again.


### Check Service Status

Command:

sudo systemctl status sshd

This shows the current status of the service.

A service can have states such as:

- Active (running)
- Inactive (dead)
- Failed


## 6. Enable a Service

To configure a service to start automatically when the system boots:

Command:

sudo systemctl enable ntp

`enable` affects automatic startup at boot.


## 7. Disable a Service

To prevent a service from starting automatically during boot:

Command:

sudo systemctl disable ntp

`disable` affects automatic startup at boot.


## ⚠️ Important Difference

Start/Stop and Enable/Disable are different things.

start → Start the service now
stop → Stop the service now

enable → Start the service automatically at boot
disable → Do not start the service automatically at boot

For example:

Running + Disabled

This means the service is currently running, but it is not configured to automatically start at the next boot.


## 🧠 What I Learned Today

- What a Linux daemon is
- Daemons are background processes/services
- How to view running processes using `ps aux`
- How to search for processes using `grep`
- What `systemd` does
- What `systemctl` does
- How to start a service
- How to stop a service
- How to restart a service
- How to check service status
- How to enable a service at boot
- How to disable a service at boot
- Difference between start/stop and enable/disable


## 💻 Commands Learned Today

ps aux

ps aux | grep ssh

ps aux | grep ntp

sudo systemctl start sshd

sudo systemctl stop sshd

sudo systemctl restart sshd

sudo systemctl status sshd

sudo systemctl enable ntp

sudo systemctl disable ntp
