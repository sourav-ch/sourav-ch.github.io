---
title: How to Github?
tags: [GitHub, Basics]
style: fill
color: primary
description: Learn basics of Github 
---
I almost use Github on a daily basis for code changes and reviews. I find it an essential for a coder, so here is a small guide on basics of Github.

GitHub is a platform built on Git that helps developers manage and share their code. It allows you to track changes, collaborate on projects, and maintain versions of your files. Here’s a simple breakdown of how to get started with GitHub and some basic Git commands:

## Creating a Repository:

A repository (repo) is where your project files live. To create one on GitHub, click on "New repository" and give it a name.
On your local machine, initialize a new repo with:


    git init


## Cloning a Repository:

If you want to work on an existing project, you can clone a repository from GitHub:


    git clone https://github.com/username/repository-name.git


## Making Changes and Committing:

After editing your files, you can stage changes with:


    git add .


Then, commit your changes with a message describing what was done:

    git commit -m "Your commit message"

## Pushing Changes:

Once you've committed your changes, push them to GitHub:


    git push origin main


## Pulling Updates:

To get the latest changes from GitHub, use:


    git pull origin main


## Creating and Switching Branches:

Branches help you work on different features without affecting the main codebase. Create a new branch with:


    git branch branch-name


Switch between branches using:


    git checkout branch-name


## Merging Changes:

Once you’re done with a branch and want to combine your work with the main branch, switch to the main branch and merge:


    git checkout main
    git merge branch-name

    
GitHub also offers features like pull requests for code review and collaboration, and GitHub Pages for hosting websites. With these basic commands, you can start using GitHub to manage your projects, track changes, and work with others efficiently!