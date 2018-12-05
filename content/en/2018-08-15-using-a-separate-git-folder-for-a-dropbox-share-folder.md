---
title: Using a separate '.git' folder for a Dropbox share folder
author: Kang
date: '2018-08-15'
slug: using-a-separate-git-folder-for-a-dropbox-share-folder
categories:
  - ICT
tags:
  - Git
  - Dropbox
---


A problem since long I have:-( was that when I use Git with Dropbox on different computers (even worse when sharing with others or on different OS), the .git folder in Dropbox keeps syncing changes, making annoying notifications in Dropbox. I googled and luckily found a blog post telling the trick on Linux, and I just made a similar workaround on Windows. Now I can use any Dropbox folder as a git repository, but store the `.git/` folder in a separate (non-Dropbox) directory by doing the following ~~four~~three steps. 

## 1. Go to the Dropbox (share) folder (e.g., the dir for this site)
Let's do it via `cd` in the `Git Bash` (it's pretty on windows),

    /c/.../Dropbox/kangyu.org

and make a separate git root folder for it:

	# [ -d "$HOME/.separate-gitroots" ] && echo "yes" # check whether the folder exists
    $ mkdir -p $HOME/.separate-gitroots # if not exists
    
## 2. ~~(Update: Ignore this step) Exclude the .git folder from Dropbox sync~~

On linux we can use the following `dropbox` command line, 

    $ dropbox exclude add .git
    Excluded:
    .git

but it does not work on Windows. For windows this step can be done in the `Dropbox App -> Preferences -> Sync -> Selective Sync` by un-selecting the `.git` folder.

## 3. Create a '.git' folder in the *separate-gitroots* for the share folder 

    $ git init --separate-git-dir=$HOME/.separate-gitroots/kangyu.org.git
    Initialized empty Git repository in C:/Users/.../.separate-gitroots/kangyu.org.git/


This step will create (or move as shown below, if you already created one in the Dropbox share folder) the git repository in `$HOME/.separate-gitroots/kangyu.org.git` instead of in the Dropbox folder `kangyu.org/.git/`. 

<img src="https://i.imgur.com/yjuu1jK.png" alt="Existing '.git' will be moved to the sep-gitroot" width="480"> 

Now the `kangyu.org/.git` will be a plain text file displayed as follows (not a folder), which is only visible when your windows is set to show the **hidden items**. 

![.git as a plain text file](https://i.imgur.com/4YHB09q.png)

It can be open in any text editor, and it contains the location of the real `.git` directory, i.e., the `kangyu.org.git` directory created in *separate-gitroots*. 

![.git file content ](https://i.imgur.com/J4kYWNn.png)

## 4. Use as a normal *un-separate* .git folder 
Although the file location is different, there shouldn't be any difference for using git. For instance check the git config. 

    $ git config user.name
    $ git remote show origin
    
Since I already have remote repository, now I can just add the remote repository (e.g. a repository on Github) where the local repository will be pushed onto.

    $ git remote add origin https://github.com/rbind/kangyu.git

From now on I can just use git without bothering about the heavy sync of changes and the annoying Dropbox notifications. Of course, you can use the same method when using other cloud service.

To be safe, I also made an additional `local copy` on my Mac and, use `.git` in the `default root`. 


#### Reference:
http://www.math.cmu.edu/~gautam/sj/blog/20160406-dropbox-git.html