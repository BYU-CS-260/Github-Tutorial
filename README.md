# Github Tutorial
Learning to use version control is absolutely essential for a programmer. If you are not using some kind of version control system already, then you should immediately start using one. Version control ensures that you can always retrieve an older version of your code in case you need to retrieve some code you have deleted. Storing your repositories in the cloud ensures that you won't lose your code, which should be one of your most precious possessions. 

Git is the preferred tool for many developers because it handles [distributed version control](http://git-scm.com/book/en/Getting-Started-About-Version-Control) so well. Outside of university projects, it is most common to work on teams when writing code, so a tool like Git that provides easy collaboration is required. It is quickly becoming a de facto standard so it is useful to understand at least its basics. Git is supported by most online software repositories, like [GitHub](https://github.com/) and [BitBucket](https://bitbucket.org/).

## Github Basics
In this tutorial, we are going to show you the minimum subset of Github commands that are necessary to complete the lab for this week.  This [tutorial](github-advanced.md) will give you a deeper understaning of the more advanced Github features if you have time to explore.

1. Create a GitHub account
[Create an account](https://github.com/signup) on GitHub if you don't have one already.

2. Set up a Personal Access Token for your Github account
   - First Select your picture or identifier in the upper right corner of the github window and select "Settings"
![](images/githubsettings.png) 
   - Scroll down to select "Developer Settings" in the bottom left of your settings page
![](images/githubdevelopersettings.png) 
   - Select "Personal Access Tokens" on the bottom left of this page
![](images/githubpersonalaccess.png)    
   - Select "Generate a new Token", create a Note to identify the token and specify "Repo" scope.
![](images/githubnewtoken.png)   
   - Select "Generate Token" and you will see the new Personal Access token in the middle of the screen.  Save it somewhere because you will be using it many times through the semester.  You will need it every time you access a github repo.  If you lose it, you can generate a new one so all is not lost, but you will find it better if you save it in a google doc or a note on your laptop.
![](images/githubtoken.png)    

3. Create a new private git repo for the ["Weather App Lab"](https://byu.instructure.com/courses/15698/assignments/598439?module_item_id=1334017)
![](images/githubclassroom.png) in Canvas

The URL for the repo should look something like 
```
https://github.com/BYUCS260/weather-app-yourgithubid
```
4. Configure git in your Cloud9 instance
If you haven't done this already, you should configure git with your name, email address, and preferred editor.
```
git config --global user.name "Daniel Zappala"
git config --global user.email daniel.zappala@gmail.com
```
Be sure to substitute your own name and email address.

5. In your terminal pane on the bottom of the Cloud9 console, change directory to your public_html folder.
```
cd ~/environment/public_html
```

6. Clone the repository onto your Cloud9 instance using the URL from github classroom and your Personal access token. Replace "YourPersonalAccessToken" with the Personal Access Token you generated in github and replace "yourgitid" with your id.
```
git clone https://YourPersonalAccessToken@github.com/BYUCS260/weather-app-yourgitid
```
![](images/githubclone.png) 

7. Change the index.html in your cloned folder, save the change, and preview the changes
![](images/change.png) 

8. Now push the changes back to github
```
cd ~/environment/public_html/weather-app-yourgitid/
git commit -a -m "Small Change"
git push
```
![](images/push.png) 

9. You should now be able to see the changes in your github browser window.
![](images/smallchange.png) 

Congratulations!  You will be saving all of your labs and creative projects in git for the rest of the class.  You will follow this same process for each assignment.
