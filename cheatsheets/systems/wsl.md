# WSL

> The Windows Subsystem for Linux lets developers run a GNU/Linux environment -- including most command-line tools, utilities, and applications -- directly on Windows, unmodified, without the overhead of a traditional virtual machine or dual-boot setup.

&mdash; Microsoft

## General settings

In the WSL system, add the following lines to `/etc/wsl.conf`:

```conf
[automount]
root = /
enabled = true
options = metadata
```

## Github

To enable repository connections to GitHub via ssh calls, in the WSL system, add the following lines to `~/.ssh/config`:

```conf
Host github.com
 Hostname ssh.github.com
 Port 443
```

## Sourcetree

To enable Sourcetree to work properly with a repo based inside WSL, make sure to correctly set the git config with the following commands:

```sh
git config core.autocrlf true
git config core.filemode false
```