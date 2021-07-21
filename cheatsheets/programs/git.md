# Git

## Repository

### Create and push new repo

Init a new repository:

```sh
git init
git add README.md
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

Source: <https://help.github.com/en/github/using-git/changing-a-remotes-url>

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

Source: <https://www.atlassian.com/git/tutorials/using-branches/git-checkout>

## Commits

- `git commit -m "message"` - directly commit staged changes with the given message
- `git commit -a` - commit all unstaged changes
- `git commit --amend` - amend staged changes to last commit

### Unstaging commits

```
git reset HEAD~1  # remove commits
```

### Rename commit messages

1. To rename one or more of the last `n` commits use:
```
git rebase -i HEAD~n
```

2. Replace the keyword `pick` in front of the commits which should be renamed by the keyword `reword` (short `r`).
3. Save and close the commit list file. 
4. The resulting commit files open automatically, change the commit message.

### Showing the changes of a commit

Use the `COMMIT` hash:
```
git show COMMIT
```

Source: <https://stackoverflow.com/questions/17563726/how-to-see-the-changes-in-a-git-commit>

### Pushing a detached head

The general command looks like:
```
git push <remote name> HEAD:<remote branch name>
```

For example:
```
git push origin HEAD:testing
```

Source: <http://redgreenrepeat.com/2018/06/08/how-to-push-a-detached-git-head/>

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

