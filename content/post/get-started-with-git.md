+++
title = "Get Started With Git, a MUST For Developers"
description = "Git is an absolute MUST, that every developer should know how to use. it makes you a lot more productive and of course version control can save you. Plus if you're looking for a job, Git is very valuable to have on a resume."
date = 2022-11-01T07:54:04-06:00
tags = ['tools', 'productivity', 'open-source']
draft = true
+++
![Get Started With Git, A Must For Developers](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xi3b5rtwyzxlockaunuv.png)
Git is an absolute MUST, that every developer should know how to use. It makes you a lot more productive and of course has version control, which can save you a ton of time and other problems. Actually getting started and understanding Git for the first time might not be too easy, so today I'll just be showing you some basic commands.
<!--more-->

## Repository Basics
A repository is a project, using the terminal you can create a repository by first going into the directory in which you want to start the repository in (using `cd <directory>`) and then typing `git init <project-name>`

Or to work in a copy of an already-made repository
`git clone <url/to/repository>`

To work in a copy of an already-made *local* repository:
`git clone <path/to/repository>`

## Staging Files
The files that you stage are essentially the files that you're going to want to be in the commit (which we will talk about soon). You can stage a file by using `git add <file-name>` or use `git add --all if you want to add all files to the stage. But I would add all the files to the stage manually to avoid anything bad.


## Committing in Git
![Git Commit Request Screenshot](https://docs.github.com/assets/cb-75044/images/help/repository/first-commit.png)

[Image Source](https://docs.github.com/en/get-started/quickstart/hello-world)

**What is a commit?** 
Ok so if you are new to Git then this might be a new term for you. A commit is usually made when you change one or multiple files (or create/delete them too). Each commit is assigned to a unique ID to track the contribution made by that commit and the time in which the commit was made.


**How to commit?** 
If you are in the terminal the command to commit is `git commit -m '<message>'`. As you can see each commit requires a message this should be short but still understandable.

## Branches
![Git Branches Screenshot](https://docs.github.com/assets/cb-23923/images/help/repository/branching.png)

[Image Source](https://opensource.com/article/19/7/create-pull-request-github)

Branches allow you to work with a different version of a repository at one time, every repository will have the main repository by default, which is what is usually the "definitive branch" or where the main production and final code will be. This makes it easier for multiple people to easily work on code. Once a branch is ready with enough commits, it is merged and then a pull request is made so it gets added to the `main` branch.

![Git Merge Gif](https://media.giphy.com/media/cFkiFMDg3iFoI/giphy.gif)


## Pull Requests
![Git Pull Request Screenshot](https://opensource.com/sites/default/files/uploads/open-a-pull-request_crop.png)

[Image Source](https://opensource.com/article/19/7/create-pull-request-github)

**What are pull requests?**
Pull requests are made when the commits are ready to be merged from one branch to another branch. There is usually one developer who verifies and reviews that the code is ready before it is pulled, which makes it so that only good code (non-malicious or bug-free code) gets into a branch.


## Conclusion
You might start to notice how Git can be useful (but maybe a little overwhelmed too), you can check out their very good docs if you'd like to go a little more in-depth into this topic.
![Git Meme](https://media.giphy.com/media/487L0pNZKONFN01oHO/giphy.gif)

I appreciate you spending your time reading this post, if you'd like to read more here you go:

[🔥  What Is Open-source? A Simple Introduction](http://localhost:1313/post/what-is-open-source/)

[🏠  Home Page](https://the-net-blog.netlify.app/)

