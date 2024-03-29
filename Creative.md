# Working Together on Creative Projects
You will want to have a shared code base for your creative projects.  
Although you could email a zip file back and forth, you will run into a 
lot of problems and it will be difficult to recover when something breaks.

When you put your code into a github project, you can each check out the 
current version and check in versions that your partner can see.

This tutorial will give you the basics, but there are a lot of other features 
that we will go over as the semester progresses.

1. [Create an account and get a Personal Access Token](Account.md)

2. Create a new repository by selecting the "New" button.

![](images/NewGitRepo.png)

3. Call it "githubtest".  Add a Readme.md file and make it visible to the public so that the TAs can grade it.

![](images/CreateRepo.png)

4. Go to the "Code" button for your new repository and copy the URL for the repository.

![](images/Clone.png)

5. Configure git in your Cloud9 instance
If you haven't done this already, you should configure git with your name, email address, and preferred editor.
```
git config --global user.name "Daniel Zappala"
git config --global user.email daniel.zappala@gmail.com
```
Be sure to substitute your own name and email address.

6. In your terminal pane on the bottom of the Cloud9 console, change directory to your public_html folder.
```
cd ~/environment/public_html
```

6. Clone the repository onto your Cloud9 instance using the URL from the "Code" button and your Personal access token. Replace "YourPersonalAccessToken" with the Personal Access Token you generated in github and replace "yourgitid" with your id.
```
git clone https://YourPersonalAccessToken@github.com/yourgitid/githubtest.git
```

7. Create an index.html in your cloned folder, save the change, and preview the changes

8. Now push the changes back to github
```
cd ~/environment/public_html/githubtest/
git add .
git commit -a -m "New Index.html"
git push
```

9. You should now be able to see the changes in your github browser window.

10. One of you should create the repository and then give permission to your partner to modify it.  
Follow these [steps](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository) to give your partner permission.  

11. Have your partner change the repository, then use the following command to get the modifications to your web server.
```
cd ~/environment/public_html/githubtest/
git pull
```
