---
title: "Git quick steps"
author: Kang
date: '2015-01-07'
slug: git-quick-steps
categories: []
tags:
  - Git
---

# Quick setups for using Git and Github

… create a new repository on the command line

```
git init
git add README.md
git commit -m "first commit"
# e.g. the repo of this blog
git remote add origin https://github.com/rbind/kangyu.git
git push -u origin master
```
… or add an existing local repository to the remote from the command line
```
git remote add origin https://github.com/rbind/kangyu.git
git push -u origin master
```
…or import code from another repository
You can initialize this repository with code from a Subversion, Mercurial, or TFS project.
Import code


# Update changes
after making local changes and you wish to push to your github repository
```
git add .
git commit -m "changes"
git push -u origin master
```

# When update across devices, it needs to
** update (pull) from the remote changes**
```
git pull origin master
git commit -m "pull remote changes"
git add .
git commit -m "merge changes"
git push -u origin master
```

These steps can also be done in Rstudio without coding.

**More about Markdown**
* [GitHub Guides](https://guides.github.com/features/mastering-markdown/)
* [Markdown quick reference](https://en.support.wordpress.com/markdown-quick-reference/) 
* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) 
