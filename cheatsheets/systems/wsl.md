# WSL

> The Windows Subsystem for Linux lets developers run a GNU/Linux environment -- including most command-line tools, utilities, and applications -- directly on Windows, unmodified, without the overhead of a traditional virtual machine or dual-boot setup.

&mdash; Microsoft 


## General settings

In the WSL system, add the following lines to `/etc/wsl.conf`:

```
[automount]
root = /
enabled = true
options = metadata
```

## Github

To enable repository connections to GitHub via ssh calls, in the WSL system, add the following lines to `~/.ssh/config`:

```
Host github.com
 Hostname ssh.github.com
 Port 443
```
