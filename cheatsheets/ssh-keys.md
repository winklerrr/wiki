# SSH keys

## Create

To create a new SSH (secure shell) key:

```sh
ssh-keygen -t rsa -C "your_email@example.com"
```

## Chown

To set the correct access rights of the key files:

```sh
sudo chmod 755 ~/.ssh
sudo chmod 600 ~/.ssh/id_rsa
sudo chmod 600 ~/.ssh/id_rsa.pub
sudo chmod 644 ~/.ssh/known_hosts
```
## Add

To add a new key to the local SSH agent:

```sh
eval `ssh-agent`
ssh-add ./id_rsa
```

## Copy

To copy the newly generated SSH key:

- assuming the key has its default name `id_rsa`
- you have the `copy` alias installed from the dotfiles `bashrc`

```sh
cat ~/.ssh/id_rsa.pub | copy
```

## Convert

To convert a SSH2 key to the OpenSSH format:

```sh
# just print the output
ssh-keygen -i -f ssh2.pub

# directly write to a file
ssh-keygen -i -f ssh2.pub > openssh.pub
```
