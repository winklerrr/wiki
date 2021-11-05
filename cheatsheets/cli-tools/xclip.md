# Awesome XCLIP Cheatsheet

**Important:** xclip does not work with the linux subsystem!
For WSL use `clip.exe` instead!

## Installation

To copy/paste console output install `xclip`:

```sh
sudo apt install xclip
```

## Basic Usage

To use `xclip` do:

```sh
# copy
cat file | xclip

# paste
xclip -o
```

## Advanced Usage

To copy/paste to the system clipboard use:

```sh
# copy
cat file | xclip -selection clipboard
cat file | xclip -sel clip

# paste
xclip -selection clipboard -o
xclip -sel clip -o
```

## Alias

For better usability create an alias like:

```sh
alias "cs=xclip -sel clip"
alias "vs=xclip -sel clip -o"
```
