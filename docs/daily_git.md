# Working with Git

This will be a long page, as it will cover the regular tasks for which Git
will be used.  Those will include

* Getting an initial copy of the files
* Making one or more changes to a file or files
* Saving changes to your local copy
* Transmitting those changes to the GitHub repository.

## Getting an initial copy

As outlined in the
[Introduction](https://justbennet.github.io/GitTutorial/index.html)
this starts by making sure that you are up to date with what's in
the repository.

Since this is your first time working in this repository,
you need to _clone_ the repository.  Cloning a repository copies all of the
file from the `main` branch to your computer, where you can work on them.

This is done with the

```
$ git clone git@github.com:carpenterbennet/sample.git
```
again remembering that your GitHub username should replace `carpenterbennet`.

The above command will create a subdirectory called `sample` in whatever
directory you ran the `git clone` command.  You can tell Git to call the
local subdirectory something else, as in

```
$ git clone git@github.com:carpenterbennet/sample.git mind-lab-example
```
which would create a subdirectory called `mind-lab-example`.  The contents
will be the same, and Git will still know it came from the same place.

## Making changes

There are a number of things you an do to files that will be considered
changes: modify the contents, add a new directory/file, change the name, move
to a new directory, remove the directory/file.

### Changing a file directly on GitHub

We will start by modifying the existing `README.md` file.  We'll start
by making a change to the file on GitHub, then we'll come back to the copy
on your computer to make additional changes.

You need to be logged into GitHub, and your `sample` repository's page, which
will be something like `https://https://github.com/carpenterbennet/sample`.

By default, GitHub shows you the contents of the `README.md` file, so you
should consider that the 'landing page' for your repository (repo, hereafter).
For those wondering, the `.md` extension indicates a **Markdown** file, and
Markdown is a scheme for simplified formatting of text files.  For more
information on Markdown at GitHub (and elsewhere), see the [Mastering
Markdown](https://guides.github.com/features/mastering-markdown/) page.

You can edit files directly on GitHub, when that's appropriate.  In this case,
it is because we're only going to change the `README.md` file.  The `README`
has a shortcut pencil icon in the upper-right corner, but instead, please
click on the file name that appears above the displayed page.

That should change the view so there is a light blue line with the name of the
person who made the last change (you, in this case), a commit ID, when it
was committed, a button to view the History of this file.  Further down, there
will be a grey bar that says how many lines in the file, how big it is, and
on the right will be two buttons (Raw and Blame), a pencil icon, and a trash
can icon.

Since we want to make changes, use the pencil icon to open the file in the
GitHub editor and change the contents to look like this.

```
# Keilholz MIND Lab Git tutorial

This repository is an example for practicing with Git.

```

If you have a tall screen, you may need to scroll down to see the green
Commit changes button (and the Cancel button). Above those buttons, you'll
find two boxes under the heading **Commit changes**.  Think of the first
line like you would the subject line of an e-mail message and the box
below it for the optional extended description as the body of the message.

Because we want to illustrate what these look like, enter

```
Making the `README` informative
```

in the upper box and

```
Modified the description.

Entering an extended description for purposes of illustration.
```

Click the **Commit changes** button, which will save the changes and display
the modified file.  Sometimes the rendered page is not what you want to see,
so you can use the **Raw** button to see unrendered text.  Use the browser's
back button to go back to the rendered page.

From the rendered page, click on the **History** button, and that should take
you to a listing of the commits that have modified this page, with the newest
listed at the top.  On the right, the commit ID is typically a blue,
multicharacter string.  Clicking on it will change to a window where you can
see the old text (with the pink background) lines prefixed with a `-` (minus)
and the new text (with the green background) lines prefixed with a `+`.

In this case, this isn't particularly helpful, but consider the case where
someone has gone through and changed a variable name in 15 places....

Also note the light blue box at the top that contains the commit message.
If the commit message outlines in English what the changes were intended to
do, then someone checking on them can more easily figure out whether the
code changes do so.

### Making changes from the command line

When you change things using the GitHub interface, most actions are performed
with buttons.  Now we'll look at how to do the same thing from the command
line, which will be far more convenient if you are modifying and testing
Matlab (or Python, C++, et al.) code.

Open a window and change to the directory in which you cloned the repository.
This will be `sample` if you didn't supply a different directory name when
you cloned.

You've made changes to the code at GitHub, so what you have on your local
computer is not what you have on GitHub.  This situation will most commonly
arise when working with others who might change code without you knowing.

It is always a good idea to start by _pulling_ changes made at GitHub.  This
is done with

```
$ git pull origin main
```


