---
Title:  install python pelican
Date: "2010-12-03"
Tags: python, pelican
Category: Web
Slug: install python pelican
Author: Kang Yu
Summary: Short version for index and feeds install python pelican
---

## install python pelican ##

steps:

- 安装Python (win cmd run as admin, msiexec /i C:\python-2.7.9.msi)
- Win + R ，输入启动 powershell
- PowerShell，输入命令 python (Python 2.7.9 (default, Dec 10 2014, 12:28:03) [MSC v.1500 64 bit 	(AMD64)] on win32
	Type "help", "copyright", "credits" or "license" for more information.)
- download get-pip.py save to C:\Python27
- PS cd C:\Python27
- python get-pip-py
- To check if everything is working, just type pip at the PS command line:

Install virtualenv and virtualenvwrapper-powershell

- PS "Start-Process powershell -Verb runas" to run as admin
- in the new PS window type "Set-ExecutionPolicy RemoteSigned" press enter
- set env 

	![](http://i.imgur.com/6r1WtCN.png)

- PS C:\> pip install virtualenv
		...successfully...
- PS C:\> pip install virtualenvwrapper-powershell
		...successfully...
- mkdir $env:WORKON_HOME
- cd $env:WORKON_HOME
- PS C:\Python27\Envs>
- import-module virtualenvwrapper

- PS C:\> Get-Command *virtualenv*

`kkkkkkkk.

	CommandType     Name                                               ModuleName
	-----------     ----                                               ----------
	Alias           cdvirtualenv ->                                    VirtualEn...
	Alias           cpvirtualenv ->                                    VirtualEn...
	Alias           lsvirtualenv ->                                    VirtualEn...
	Alias           mkvirtualenv ->                                    VirtualEn...
	Alias           rmvirtualenv ->                                    VirtualEn...
	Function        add2virtualenv                                     VirtualEn...
	Function        CDIntoVirtualEnvironment                           VirtualEn...
	Function        Copy-VirtualEnvironment                            VirtualEn...
	Function        GetVirtualEnvData                                  VirtualEn...
	Function        Get-VirtualEnvironment                             VirtualEn...
	Function        LooksLikeAVirtualEnv                               VirtualEn...
	Function        NewVirtualEnvData                                  VirtualEn...
	Function        New-VirtualEnvironment                             VirtualEn...
	Function        Remove-VirtualEnvironment                          VirtualEn...
	Function        Set-VirtualEnvironment                             VirtualEn...
	Function        showvirtualenv                                     VirtualEn...
	Function        virtualenvwrapper_get_python_version               VirtualEn...
	Function        virtualenvwrapper_get_site_packages_dir            VirtualEn...
	Application     virtualenv.exe
	Application     virtualenv-3.4.exe

kkkkkkkkkkkkkkkk



install a virtual env with name "pelican" 
- mkvirtualenv pelican --no-site-packages
- after install show: (pelican)PS C:\Python27\Envs>
- run: pip install pelican
- Once Pelican is installed, you can run pelican --help to see basic usage options.
- pip install --upgrade pelican

- mkdir blogfoldername 
- cd blogfoldername
- pelican-quickstart

in Git Bash
- cd c:/xxx/blogfoldername (use "/" in Git Bash, different from the use of backslash "\"in PS)



## Write an artical using Markdown ##
Metadata syntax for Markdown posts should follow this pattern: 

	Title: My super title
	Date: 2010-12-03 10:20
	Tags: thats, awesome
	Category: yeah
	Slug: my-super-post
	Author: Alexis Metaireau
	Summary: Short version for index and feeds

This is the content of my super blog post.


## theme 
cd to the directory where you want to put the themes, and start to clone 
`git clone --recursive https://github.com/getpelican/pelican-themes`

or define the directory by adding the path to the end of code
`git clone --recursive https://github.com/getpelican/pelican-themes ~/pelican-themes`  

specify the THEME = "pelican-themes/theme-name" in the pelicanconf.py, and make html in bash
`pelican -s pelicanconf.py`.  


## publish after local testing 



### How can I use a static page as my home page?
to see more refer to [Pelican FAQs](https://github.com/getpelican/pelican/blob/master/docs/faq.rst)
The override feature mentioned above can be used to specify a static page as your home page. The following Markdown example could be stored in content/pages/home.md:

Title: Welcome to My Site
URL:
save_as: index.html

Thank you for visiting. Welcome!
If the original blog index is still wanted, it can then be saved in a different location by setting INDEX_SAVE_AS = 'blog_index.html' for the 'index' direct template.