---
layout: post
title:  "Getting started with github pages"
date:   2016-11-19 16:34:48 +0000
categories: jekyll gettingstarted
---

This post describes how to configure your github repo to use the /docs folder as the source code for the repo's documentation that will be automatically published in github.io.

# Configuring the documentation folder

1. In the repo's [**Settings**]({{ site.baseurl }}/pages/RepoSettings.html), in the [**GitHub Pages**]({{ site.baseurl }}/pages/GitHubWSettings.html) section, set (or ensure that) the doc source to _none_.

2. Set the current branch to [**master**]({{ site.baseurl }}/pages/MasterBranch.html).
2. [Create (or confirm the existence of) a **/docs** folder in repo]({{ site.baseurl }}/pages/NewFile.html). To create a folder, if necessary, create a **/docs/index.md** file and enter some simple content in markdown.
3. In the repo's **Settings**, in the **GitHub Pages** section, [set (or ensure that) the doc source to _master branch /docs_ folder]({{ site.baseurl }}/pages/GitHubPagesSetting.html).
4. Wait about a minute and make sure that no errors are reported in the **GitHub Pages** section of the repo's **Settings** page. 
5. If no errors are reported, check to see if your documentation is visible at https://**<account\>**.github.io/**<repo name\>**. For example, this content will be visible at [https://rbwatson.github.io/TCO476-new5/](https://rbwatson.github.io/TCO476-new5/)

# Create a new Jekyll documentation project

If the preceding steps produce a valid documentation topic entry in github.io, you can proceed to create a new Jekyll project from a system that has git and Jekyll installed (e.g. you AWS EC2 server).

1. From the root folder of your user account on your AWS EC2 server, do one of these: 
	1. If you have not cloned the repo, clone the documentation repo created above and go to the **/docs** folder of the repo.
	2. If you have already cloned the repo, then refresh the content of the repo on the server by going to the folder with the repo and entering the following at the command line:<br>
```git pull origin master```<br>
and go to the **/docs** folder of the repo.
2.  Create a new Jekyll documentation template in the **/docs** folder, by entering this at the command line: <br>
```jekyll new . --force``` <br>
3. Rename **index.html** to **index.md** and add any additional markdown to the page (carefully so as to not create any errors when the documentation is built).
4. Add all the new files to git:<br>
```	git add *.*```<br>
```	git add _posts/*.*```<br>
```	git add css/*.*```<br>
```	git commit -a -m "creating new Jekyll doc project"```<br>
```	git push origin master```<br>
This should push the documentation files to the github server, which should cause it to build automatically (within a few seconds, if not immediately)
5. Wait about a minute, refresh the **Settings** page of the repo, and make sure that no errors are reported in the **GitHub Pages** section of the repo's **Settings** page. 
6. If no errors are reported, check to see if your updated documentation is visible at https://**<account\>**.github.io/**<repo name\>**. For example, this content will be visible at [https://rbwatson.github.io/TCO476-new5/](https://rbwatson.github.io/TCO476-new5/)

# Documentation updates

After the preceding is successful, new topics and documentation can be added and updated using normal git protocol. That is, a **dev** branch can be created from the **master** branch and then edited and tested. 

When the updated content in the **dev** branch is ready to publish, a pull request can be created to update the **master** branch. Once the **master** branch documentation content has been merged and updated, the content at https://**<account\>**.github.io/**<repo name\>** will be updated automatically (within a minute or so, normally).

# Additional documentation

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
