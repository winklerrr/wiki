# WSL

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
