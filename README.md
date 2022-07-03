# Github Tutorial
Learning to use version control is absolutely essential for a programmer. If you are not using some kind of version control system already, then you should immediately start using one. Version control ensures that you can always retrieve an older version of your code in case you need to retrieve some code you have deleted. Storing your repositories in the cloud ensures that you won't lose your code, which should be one of your most precious possessions. 

Git is the preferred tool for many developers because it handles [distributed version control](http://git-scm.com/book/en/Getting-Started-About-Version-Control) so well. Outside of university projects, it is most common to work on teams when writing code, so a tool like Git that provides easy collaboration is required. It is quickly becoming a de facto standard so it is useful to understand at least its basics. Git is supported by most online software repositories, like [GitHub](https://github.com/) and [BitBucket](https://bitbucket.org/).

## Github Basics
In this tutorial, we are going to show you the minimum subset of Github commands that are necessary to complete the lab for this week.  This [tutorial](github-advanced.md) will give you a deeper understaning of the more advanced Github features if you have time to explore.

1. Create a GitHub account
[Create an account](https://github.com/signup) on GitHub if you don't have one already.

Step 2: (OPTIONAL) Configure an SSH key
Using an SSH key will allow you to interact with your GitHub repositories without having to type your password regularly. If this interests you, go back and do the setup for SSH with your Digital Ocean server in the optional activity, then come back here.

You can use the official GitHub instructions (Links to an external site.), which has tabs for both OS X and Windows. Note, if you have setup your SSH key with your Digital Ocean machine, then all you should need to do is copy your public key to your GitHub account as described here (Links to an external site.).

Step 3: Create a GitHub respoitory
In your account, create a new repository called gitpractice.

Step 4: Configure git
If you haven't done this already, you should configure git with your name, email address, and preferred editor.

git config --global user.name "Daniel Zappala"
git config --global user.email daniel.zappala@gmail.com
git config --global core.editor emacs
Be sure to substitute your own name, email address, and preferred editor. You might use vim or nano.

Step 5: Create a directory with a test file
On your local machine, create a new directory called git1:

mkdir git1
cd git1
In this directory, use the editor of your choice to create a file called test.txt with the following lines:

One
two
three
Step 6: Initialize a git repository, commit your changes and push them to GitHub
On your local machine, and inside the git1 directory, initialize a git repository and commit your changes

git init
git add test.txt
git commit -m "Added a file"
Note: you can add all files and folders with changes with git add . (including the period)

You now have a local git repository with this file committed. When you supply the "-m" flag, you put your commit message right on the command line. If you omit the "-m" flag, git will open the editor you configured and you can write the commit message in an editor. 

Before you move on, run the git status command and you will see that you have one commit that has not been pushed to the remote repository on GitHub.

Next, you will setup your repository so you can push your changes to your GItHub account. This is called a "remote" repository. You want to do this so that your files are all stored on GitHub, in case your laptop crashes.

git remote add origin git@github.com:zappala/gitpractice
git push -u origin master
Be sure to subsitute your username above, and don't use mine. You can click on the "Clone or download" button in GitHub to get the full path name for your own repository.

Important
If you are using HTTPS (and NOT using SSH keys), then your GitHub links will look like this: https://github.com/zappala/gitpractice.git.

If you are using SSH keys, then you github links will look like git@github.com:zappala/gitpractice.

There is a small link in the Clone or Download dialog that lets you switch between these.

Check that it works
You should be able to view your repository on GitHub and see this file in the repository. If you run git status you will see that your local repository is in sync with the remote repository on GitHub.

Step 7: Make additional changes
Make some additional changes to test.txt. Then commit them. This time, we'll use "-a" to add the file to be committed and we'll leave off "-m" so that it will open an editor instead:

git commit -a
After you enter a commit message, then you can push your changes to the server:

git push
You should notice your changes on GitHub. You can also see all the changes on your local machine with:

git log
