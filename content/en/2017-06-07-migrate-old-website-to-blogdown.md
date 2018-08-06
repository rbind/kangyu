---
title: migrate old website to blogdown
author: Kang
date: '2017-06-07'
slug: migrate-old-website-to-blogdown
categories: []
tags: []
---

eh, my old website has been dead since >2 years. I have now finaaaaaaaaaaaly migrated to [blogdown](https://github.com/rstudio/blogdown), a great r package developed by [Yihui](http://yihui.name), based on [Hugo](https://gohugo.io). This site is currently deployed on Netlify - blogdown simply makes a website a folder of static files, and can be put on any web [server](https://bookdown.org/yihui/blogdown/deployment.html).


as from a while ago, rstudio interface enables the Terminal (Shell) tab, right next to the Console, I can simply update my changes in the Terminal tab by runing following three lines, isn't it a joy!
```
git add .
git commit -m "updates"
git push -u origin master
```