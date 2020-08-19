# Git & GitHub 101

## Install Git

```Shell 
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install git
```

## Link git to your Github account

### Create a SSH key
To login into github you need a **SSH-key**. Here is how to generate one.

1. Create an SSH key linked to your email.
```shell
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
2. Save it to default location: (/home/*user_name*/.ssh/id_rsa): [Leave blank and press `Enter`]

### Add the SSH key to your github account

1. With xclip, copy the content of the file to your clip
```shell
sudo apt-get install xclip
xclip -sel clip < ~/.ssh/id_rsa.pub
```

2. On github, go to your **Settings** > **SSH and GPG keys** > **New SSH key**

3. Paste the key, add a title and save it.

## Cheatsheet
[PDF cheatsheet](https://github.github.com/training-kit/downloads/fr/github-git-cheat-sheet.pdf) from github.com

### How to: Commit your code
```shell
git add file.js # Add your new files.
git commit # Commit the changes
git push # Update a Github branch with local changes
```

### How to: Create a branch and commit your code
```shell
git branch bugFix # Create a bugFix branch
git checkout bugFix # Switch HEAD to bugFix branch
git commit
```

### How to: Merge branches
```shell
# To merge branch "bugFix" to "master", be sure to HEAD to master branch:
git checkout master
git merge bugFix # merge bugFix to master
```
### How to: Rebase
Useful to merge and "remove" (make invisible forever) a branch.

```shell
# To rebase branch "bugFix" to "master", be sure to HEAD to bugFix branch:
git checkout bugFix
git rebase master

# Then rebase master into bugFix.
git checkout master
git rebase bugFix
```


