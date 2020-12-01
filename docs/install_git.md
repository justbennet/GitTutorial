# Installing Git

In the following examples, the `$` at the beginning of each line
indicates the prompt, and the command you should enter follows it.
Lines not beginning with a prompt of some kind are output.

## Mac

We will use `git` from a Terminal window command line on the Mac, and
it should be installed by default.  To test that, open a Terminal window,
and follow this example.

```
$ git --version
git version 2.3.5
```

## Linux

We will also use Git from a Terminal window on Linux.  Testing is the
same on Linux as on the Mac.  On my older Linux machine, I get

```
$ git --version
git version 1.8.3.1
```

## Windows

Git is not installed on Windows by default, and neither is the Bash
shell (command prompt) that we will be using.  GitHub provides a
Windows installer that installs both Git and a Bash shell program
from which you can use Git.

Download the [Git for Windows
installer](https://git-scm.com/download/win) and run it.  See
the fully (I think) commented step-by-step of [installing
Git for
Windows](https://justbennet.github.io/GitTutorial/win_git_install.html)

Once it is installed, there should be a 'Git Bash' program available
from the Start Menu.  Open that, then use the same command as above
to confirm.

```
$ git --version
git version 2.29.2.windows.2
```
