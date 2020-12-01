# Creating a new repository

It is often easiest to create new repository at GitHub using the
web interface.  I typically create a new repository only with
a license (I tend to pick MIT) and README file.  Both of those
are generally useful, and modifying the README file is a simple
place to start using Git.

So, log into your GitHub account.  I will use the GitHub username
`carpenterbennet` in what follows.  You should subsitute your own
GitHub username.

If you are just getting started with Git as a Windows user and you
have not already set up Windows Services for Linux (WSL) or Cygwin
or some other facility that provides a Bash (Linux) command line
and got familiar with it, then you should probably install the Git
Bash program from

[Git Bash installer](https://git-scm.com/download/win)

You will find it vastly easier to set up SSH Keys for your GitHub
account if you have not already done so.  Please see

[Adding an SSH key](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Mac and Linux users should have SSH already installed and can run

```
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```

Doing so will make it so you do not have to enter your GitHub
username and password each time.  What follows assumes that you
have set up SSH keys.  If you don't, you'll get username and
password prompts.

## At GitHub

You should get a page that opens to your profile, and there will be a
set of tabs from which you can choose **Repositories**.  This is
shown in the following screen shot, where **Repositories** is
show with an orange underline.

![image](https://github.com/justbennet/GitTutorial/raw/main/images/github_repo_tab.png)

From there, click on the green **New** button.  That will take you to a page
on which you enter the following information.

* The **Repository name** (I recommend never using spaces in a repository name)

  For this tutorial, please use the name `sample`.
* An optional **Description** (leave blank for this example)
* Choose **Public**
* Check the box to **Add a README file**.
* Check the box to **Choose a license**
  If you do not know which type you need/want, then choose 'MIT License'.

Note the text that says

> This will set `main` as the default branch. Change the default name in your settings.

You will want to remember that later.

Now click the green **Create repository** button.  That should result in a page that
looks something like this (with your GitHub name instead of `carpenterbennet`.

![image](https://github.com/justbennet/GitTutorial/raw/main/images/new_repo_page.png)


