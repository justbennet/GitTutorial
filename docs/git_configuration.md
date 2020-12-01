# Configuring Git on your computer

To do the following setup tasks, you need to have the terminal window from
which you will use Git open.  On Linux and Mac, this will be a standard
terminal window.  On Windows, this is likely to be the Git Bash terminal
window.

## Setting your identity

Part of the strength of Git is that it stores not only what changes were
made but who made them and when.  That makes it easier to find whoever made
that pesky change and ask them about it, or to find whoever fixed that bug
and thank them.

Most of the time, you will set your identity globally; that is, your identity
will be the same for all your work.  If you start working on other, more
public open source projects, you may wish to set your identity to something
else so that e-mail and other traffic is separated from your main name and
account.  To set your identity globally, use the following commands in the
terminal window.

```
$ git config --global user.name "Carpenter Bennet"
$ git config --global user.email "carpenterb@hotmailx.com"
```

If you elect to use a private e-mail address with GitHub,
then use that same e-mail address for the user.email value,
e.g. username@users.noreply.github.com replacing username with your
GitHub one.

## Setting your editor

If you do not already use `vi` or `emacs`, you should start with `nano` as
your default Git editor.  This can be set with

```
$ git config --global core.editor "nano -w"
```

Nano should be installed on virtually all modern Linuxes, on the Mac, and now
with Git Bash.

You can set these same options on a per-repository basis to override the
global values set here.

See [Setting Up
Git](https://swcarpentry.github.io/git-novice/02-setup/index.html) for a
lengthier explanation and for some editor settings for alternate editors.
