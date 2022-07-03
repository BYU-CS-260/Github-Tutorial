# Learning Git

The best place to learn Git is to use the free [Pro Git book](http://git-scm.com/book). 
Read Chapters 1 and 2 and you will learn what you need to be productive for individual projects in this class.

You can also use this [interactive Git tutorial](https://try.github.io/levels/1/challenges/1). 
Here is a useful [Git cheatsheet](https://www.git-tower.com/blog/git-cheat-sheet/).

##Configuration
Github has a new requirement that you use ssh keys, so you will need to [set that up first](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).  
I recommend not using a password when you do the ssh-keygen.  So you should run the following commands in your terminal:
```
ssh-keygen -t ed25519 -C "youremail@youremailhost.com"
eval "$(ssh-agent -s)"
touch ~/.ssh/config
```
Then edit ~/.ssh/config to contain the following
```
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```
Then run the following commands
```
ssh-add  ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```
You should then copy the output of the "cat" command and log into your github account in your web browser and 

- In the upper-right corner of the github page, click your profile photo, then click Settings
- In the user settings sidebar, click SSH and GPG keys.
- Click New SSH key or Add SSH key.
- In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
- Paste your key into the "Key" field.
- Click Add SSH key.
If "git push" asks for a username and password, you can run the following command to specify that you want to use your ssh key:
```
git remote set-url origin git@github.com:your_username/repo_name.git
```
I recommend doing some configuration for your name, email, and editor:
```
git config --global user.name "Daniel Zappala"
git config --global user.email daniel.zappala@gmail.com
git config --global core.editor <emacs or nano or vim>
```
## Common Commands
The commands I use most often:

### Create Repositories
- `git init` : initialize a new repository
- `git clone <url>` : clone a repository
### Work With A Local Repository
- `git log` : view all previous commits
- `git log -p` : view all previous commits with the diffs
- `git status` : list changed and new files
- `git diff` : view changes to files
- `git add .` : add all new files to a repository
- `git commit -a` : commit all changes to all files
- `git tag <name>` : mark current commit with a tag
### Update a Repository and Publish Changes
- `git remote add <remote> <url>`: add a remote repository
- `git pull <remote> <branch>` : download commits from a remote repository and merge them
- `git push <remote> <branch>` : upload commits to a remote repository
- `git push --tags` : push tags to a remote repository

In addition to these commands, it is useful to create a `.gitignore` file containing paths and file extensions you would like to ignore. For example, this might include backup copies created by your editor, configuration files that include important passwords, or (later in the course) node.js modules.

### Branching and Workflow (Advanced Material)
Once you start participating in shared projects, then Chapters 3 and 5 of Pro Git will help you with branching and workflow models. I also recommend this [example workflow](http://nvie.com/posts/a-successful-git-branching-model/), which you can trim down for smaller projects. There are some good [thoughts about workflows](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow) by Atlassian.

The commands I use most often:

- `git branch` : list all branches
- `git checkout <branch>` : check out an existing branch
- `git checkout -b` : create and check out a new branch
