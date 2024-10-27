# greenwood-library-website

## Create Repository on GitHub

The first step is to create a repository on GitHub named, "greenwood-library-website".

![]()
![GitRepo](./img/1%20Git_workspace.png)

## Clone Remote Repo to Local Repo

Here I practiced cloning by cloning the remote github repo I created in the previous step to my local repo

![clone](./img/2%20Git_Clone.png)


## Create Webpages

Here, I will be creating webpages on my local repo. The webpages I created are home.html, about_us.html, events.html, and contact_us.html

![webpages](./img/4%20Create%20web%20pages.png)


## Stage Changes

Using git add, I will be staging the webpages I created as well as the img page for my images

![staging](./img/5%20Staging.png)


## Commit Changes

Here, I used the "git commit -m " command to commit the changes to my main

![Commit](./img/6%20Commit.png)

## Push Changes

Here I pushed the changes to my remote repo 

![Push](./img/7%20Push%20to%20remote.png)


## Create Pull Request and Merge Request on GitHub

I created a pull request on github. See images below

![PullMerge](./img/10%20Merge%20Pull%20Request.png)
![PullMerge2](./img/10%20Merge%20Pull%20Request%202.png)

## Problem Encountered with .DS_Store file on Mac

### Problem 1
While trying to switch from add-book-reviews branch to main, I experienced a problem where I couldn't switch because of the hidden file, .DS_Store.
To resolve this, I decided to stage and stash the file. In the past, I had staged, committed and pushed the .DS_Store file. However, the .DS_Store remains uncommitted and continues to pose a problem.
To switch to main, I had to stage and stash the .DS_Store file on my branch first using `git add . && git stash`

![Problem1](./img/11%20Git_Problem_DS_Store.png)

### Problem 2

After I was able to switch to main, I tried to pull my merged changes from my remote to my local. This didn't work because of the .DS_Store file as well. After doing some research on how to navigate this problem, I decided to create a `.gitignore` file and add the .DS_Store file to it using `echo`

![Problem2](./img/11%20Git_Problem_DS_Store%202.png)
![Problem3](./img/11%20Git_Problem_DS_Store%203.png)

After creating the `.gitignore` file and adding the .DS_Store file to it, I tried to switch to the "add-book-reviews branch to see if I would experience any issues and I got an error as a result, so I tried using `find . -name .DS_Store -print0 | xargs -0 git rm --ignore-unmatch` to ignore all .DS_Store files that have already been committed. This didn't work however but I got feedback asking me to --cached to keep the file or -f to force remove it. So I proceeded to remove the first remove the cached file using `git rm --cached .DS_Store` before using `find . -name .DS_Store -print0 | xargs -0 git rm --ignore-unmatch`.
To ensure that this doesn't cause an issue for me again, I decided to use the following commands to ignore the .DS_Store file globally, `echo ".DS_Store" >> ~/.gitignore_global`, `echo "._.DS_Store" >> ~/.gitignore_global`, `echo "**/.DS_Store" >> ~/.gitignore_global`, `echo "**/._.DS_Store" >> ~/.gitignore_global`, `git config --global core.excludesfile ~/.gitignore_global`. After running those commands, I tried to run my pull request again on main, however, I got an error: `Your local changes to the following files would be overwritten by merge .DS_Store`. 

![problem4](./img/11%20Git_Problem_DS_Store%204.png)


## Pull Remote to Local

This error prompted me to go on `GitHub` and directly delete the merged .DS_Store file on my remote repo. Which then allowed me to pull my main on the remote to my local

![Pull](./img/12%20Git_pull.png)


## New Change - Update Event Branch

I created a new branch called Update Events and added a new webpage called "Update_events.html". After making the change, I staged the change, committed it and then pushed it to git. This created a pull request on my remote git and I went ahead to merge the change with my main.

![Update_Events](./img/13%20Update%20Events.png)
