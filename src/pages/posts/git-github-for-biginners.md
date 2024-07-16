---
title: Git and GitHub for biginners
slug: git-github-for-biginners
date: 2021-4-18
author: Atharva Joshi
read_time: 5
tags: [GitHub]
order: 1
hero: https://images.datacamp.com/image/upload/v1651047046/image8_0e61d0dad8.png
draft: false
---

# Getting started with 🧠 Git and GitHub 💬.

## What is GIT?

So, what is Git in a nutshell? This is an important section to absorb, because if you understand what Git is and the fundamentals of how it works, then using Git effectively will probably be much easier for you.
<Strong>A free and open source version control system. </Strong>

## What is Version Control?

<Strong>
“The management of changes to documents, computer programs, large web sites and other collections 
of information.”
</Strong>
It is basically a way that we as programmers track our code changes, we basically save an initial version of 
our code into GIT. When we update code we can save it into GIT again and again and again and throughout 
time as our code continues to change we can look back at all of the changes we ‘ve made over time. This 
helps us to see what we did and when as well as track down bugs or go back to previous version of the code 
if we need to.

## Terms used in this article.

- Directory → Folder.
- Terminal or command line → Interface for Text Commands.
- CLI → Command Line Interface.
- cd → Change Directory.
- Code Editor → Word Processor for Writing Code (VSC).
- Repository → Project, or the folder/place where your project is kept.
- GitHub → A website to host your repositories online.

## Git 🆚 GitHub

<strong>GIT</strong> is the tool that tracks the changes in your code over time whereas **GITHUB** is a website to host
your repositories online. Being online it makes easy to work in groups with other people and organize
your projects into a portfolio for you to show potential employers.

## Git Commands

Here are some of the GIT commands we are going to cover in this section of the book that you are going to
type in Terminal (MAC) or command line (WINDOWS) in your computer. They are:

1. **clone:**  Bring a repository that is hosted somewhere like Github into a folder on your local machine.
   For example if there is a repository that is not on your local machine but it’s on Github and you want
   to bring it down on your local machine, So you can use it locally.

2. **add:**  Track your files and change in Git.
   When you have updated files or created or deleted files in folder you’re gonna want to tell Git that
   you made changes and that you would like to get track of those changes so you use the add
   command.

3. **commit:** Save your files in Git
   As I said earlier that Git is there for you to save the changes of your code so you do that through a
   commit and we call it committing your changes.
4. **push:**  Upload Git commits to a remote repository, like Github
   Once you have made changes locally on your computer and you are ready to put them in Git. You
   tell Git to track them through the add command you save your files to get through the commit
   command and then you upload your files to a place like Github or another what we call remote
   repository or Github alternative like Bitbucket, Gitlab and there’s many of them you do this through
   push command.

5. **pull:** Download changes from remote repo to your local machine, the opposite of push.
   When there are changes to you code on Github and you want to bring those to your local machine
   then you use the pull command. You pull down the changes from the remote repository.

## Creating repository on local machine.

1. Go into the folder directory which you want to push.

```bash
$ cd folder-path

```

2. Initialize your project for git.

```bash
$ git init

```

3. Add all your project files.

```bash
$ git add .

```

4. Commit the files and the message.

```bash
$ git commit -m “initial commit”

```

5. Now go to your github dashboard and create a new folder.

![https://miro.medium.com/max/875/1*5MDsyiLW4DgS4xIa9vpCmA.png](https://miro.medium.com/max/875/1*5MDsyiLW4DgS4xIa9vpCmA.png)

6. Enter a name for your repository and click the **"Create repository"** button.

![https://miro.medium.com/max/875/1*5MDsyiLW4DgS4xIa9vpCmA.png](https://miro.medium.com/max/875/1*u3GeRSVt9ifCFDMUOpb1cA.png)

7. Copy URL to the clipboard.

![https://miro.medium.com/max/875/1*6rIb_rcFHRjCdxcyhpgSNQ.png](https://miro.medium.com/max/875/1*6rIb_rcFHRjCdxcyhpgSNQ.png)

8. Go back to your terminal and set the origin by pasting the url from the clipboard.

```bash
$ git remote add origin {paste the copied URL from clipboard}

```

9. Push the files from local machine to your github repository

```bash
$ git push -u origin master

```

## Closing and a final conclusion

In this post you discovered Git And GitHub for beginners. You learned that:

- What is Git.
- What is Version Control System.
- Git 🆚 GitHub.
- Git commands.
- Pushing source code to GitHub.

Do you have any questions about GIT and GitHub or this post? Leave a comment and ask your question and I will do my best to answer it.

## Sources for the above article / Call-to-Action

[Image Source](https://medium.com/react-native-institute/how-to-use-git-with-react-native-687c12431e36)

[Content Source](https://github.com/atharva20-coder/intro-to-git-github/blob/main/intro%20to%20git%20and%20github.pdf)

## Dowload the full guide for version control system with pictorial explaination

[**Download Link :**](https://github.com/atharva20-coder/intro-to-git-github/raw/main/intro%20to%20git%20and%20github.pdf)

[**Click 👉 to 👉Download the 📙 :**](https://github.com/atharva20-coder/intro-to-git-github/raw/main/intro%20to%20git%20and%20github.pdf)
