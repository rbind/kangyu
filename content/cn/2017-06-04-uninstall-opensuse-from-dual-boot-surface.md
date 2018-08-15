---
title: 删掉Surface双系统的OpenSUSE
author: Kang
date: '2017-06-04'
slug: uninstall-opensuse-from-dual-boot-surface
categories:
  - cn
tags:
  - linux
  - Dual boot
---


#### 1.剧情回顾
装了OpenSUSE 有一段时间了，很少用也没有太多时间去研究，有所以决定卸载掉！而且对OpenSUSE界面也没有什么感觉，可能是最要从ubuntu开始，有了先入为主的错觉。

看了半天的攻略，稍微有点麻烦，准备好了win10的USB恢复盘，先删了swap分区，然后OpenSUSE运行正常，想想还是先不删了。。。容我再纠结几年!


#### 2.续集
`......一年后`

终于把dual boot的OpenSUSE删了，很庆幸事先备好的Win10恢复盘没有派上用场！

事实证明光删了那个十几个G的swap分区是不影响dual boot的。后来通过Windows自带的分区工具，`This PC` -> `Right Click` -> `Manage` -> `Disk Management` （或者在命令栏运行`diskmgmt`）直接格式化了OpenSUSE所占用的分区。然后，可利用`Extend Volume`把分区合并到系统分区，当然也可以当做独立的分区使用。