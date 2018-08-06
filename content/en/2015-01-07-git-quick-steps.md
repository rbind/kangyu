---
title: Git quick steps
author: Kang
date: '2015-01-07'
slug: git-quick-steps
categories: []
tags:
  - Git
---

# Quick setups

… create a new repository on the command line

```
git init
git add README.md
git commit -m "first commit"
# e.g. the repo of this blog
git remote add origin https://github.com/rbind/kangyu.git
git push -u origin master
```
…or push an existing repository from the command line
```
git remote add origin https://github.com/rbind/kangyu.git
git push -u origin master
```
…or import code from another repository
You can initialize this repository with code from a Subversion, Mercurial, or TFS project.
Import code

# Update changes
after making local changes and you wish to push to your github repo
```
git add .
git commit -m "changes"
git push -u origin master
```

# When update across devices, it needs to
** update from online(remote) changes**

```
git pull origin master
git commit -m "pull remote changes"
git add .
git commit -m "merge changes"
git push -u origin master
```

# these steps can also be done in the Rstudio without coding

**Markdown guide**

https://guides.github.com/features/mastering-markdown/ 

https://en.support.wordpress.com/markdown-quick-reference/ 

https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet 
