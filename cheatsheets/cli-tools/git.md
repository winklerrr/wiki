# Git

## Repository

### Create and push new repo

Init a new repository:

```sh
git init
git add .
git commit -m "first commit"
```

Connect with an existing repository online:

```sh
git remote add origin SSH-URL-HERE
git push -u origin master
```

### Change remote URL from HTTPS to SSH

To show remote URLs of a local repository:

```sh
git remote -v
```

To change the remote URL of a local repository:

- replace `<USERNAME>` and `<REPOSITORY>` accordingly

```sh
git remote set-url origin git@github.com:<USERNAME>/<REPOSITORY>.git
```

### Reset commit history

In your local repository, remove all git entries:

```sh
rm -rf .git
```

Then initialize a new git repository as usual and push it to the remote origin.

## Branches

- `git branch` - show local branches and currently checked out branch
- `git branch -l -r` - list all remote branches
- `git branch -d <branch-name>` - delete branch
- `git checkout -b <new-branch>` - create and checkout new branch

### Only show the current branch

Print the current branch:

- `git branch` - the one with the asterik at the beginning is the current branch
- `cut` - to cut off the beginning of the resulting string (starting at the 3rd position)

```sh
git branch | grep '*' | cut -c 3-
```

### Checking out a remote branch

```sh
git fetch --all
git checkout --track <remote-branch>  # create a new local branch which tracks the remote one
```

## Commits

- `git commit -m "message"` - directly commit staged changes with the given message
- `git commit -a` - commit all unstaged changes
- `git commit --amend` - amend staged changes to last commit

### Unstaging commits

```sh
git reset HEAD~1  # remove commits
```

### Rename commit messages

1. To rename one or more of the last `n` commits use:

```sh
git rebase -i HEAD~n
```

1. Replace the keyword `pick` in front of the commits which should be renamed by the keyword `reword` (short `r`).
1. Save and close the commit list file.
1. The resulting commit files open automatically, change the commit message.

### Showing the changes of a commit

Use the `COMMIT` hash:

```sh
git show COMMIT
```

### Pushing a detached head

The general command looks like:

```sh
git push <remote name> HEAD:<remote branch name>
```

For example:

```sh
git push origin HEAD:testing
```

## Configuration

### Check and set credentials

To check your current git credentials:

```sh
git config --list  # to see all the config

# to just check name and email
git config user.name
git config user.email
```

To set new credentials use:

```sh
# --global is optional
git config --global user.name "Sandro Winkler"
git config --global user.email "you@domain.com"
```
