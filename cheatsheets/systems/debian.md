# Debian

Debian has three different release class:

- stable
- testing
- unstable

The default Debian installation is based on the stable release class.
Additionally, each release has a codename.

## Upgrading to Testing

To upgrade Debian to the testing release:

```sh
cd /etc/apt/

# create backup
sudo cp sources.list sources.list.backup
```

In `sources.list` the release name (e.g. `buster`, `bullseye`, etc.) or the release class (i.e. `stable`, `testing`, etc.) needs to be set.
Furthermore, the server needs to be chosen. 
A list of all avaible Debian servers can be found on <https://www.debian.org/mirror/list>.

### Example

So, for example, this can be set:

```sh
deb http://ftp.de.debian.org/debian/ testing main
```

Now update the system:

```sh
sudo apt update
sudo apt upgrade
sudo apt dist-upgrade
```
