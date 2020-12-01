# Why Git and GitHub

Git has become the predominant program for managing computer code.  It's
basically a system to enable one or more people to keep track of what
changed in their code over time, from first draft on.  It enables you
to make different versions so you can work on updates or fixes or new
capabilities without breaking what you already have.

GitHub is a web site that enables you to share your code, and it provides
a fairly convenient way to communicate with other people who use your code.
They can submit questions and report problems there; they can help you fix
broken things; they can add bells and whistles; whatever.

It's also a sort of a _de rigeur_ thing if you want people to think you're cool
and are part of the 'coder culture', which is itself cool.  And we all know
how important _cool_ is!  ;-)

Mostly, though, you might find it really useful in your work.  The next
section is a narrative of how Git is often used.

# A day in the life

Let's assume for the moment that your group already has Git and GitHub
set up, but you're coming into a new way of working.  This is what your
introduction to how this all works might be like.

You get your favorite morning beverage and log into your computer.  You
found a nice way to vectorize something that's been a nested for loop.  Now
you want to add it to the group's code base.

The first thing to do is make sure you're up to date with everyone else's
changes, so you _pull_ those.

Next you make a new _branch_ to work on your nifty new idea.

You modify an existing file to use the new technique, and you add a new
file that does nothing but test the new technique's results against the
old.

A couple of hours (or even days) go by getting the vectorization right,
and it now works!

You _commit_ all the changes you've made along with some comments in
the _commit message_ about what you've done, why, maybe you have to
cite someone's article for the source of the numerical method, etc.

You _push_ your new branch to GitHub.

You log into GitHub and submit a _pull request_ (PR) asking someone
to look at your code, comment and request changes if necessary, and
then to _merge_ what you did into the _main_ branch.

You check out the main branch again so any further work is based on
the current state, and you pull again just to be sure.

Lunch!

# The tour

On the left there are buttons corresponding to steps in getting
started with Git and GitHub.  We'll be starting from scratch,
creating a brand new repository, adding some files, saving changes,
looking at how we might work with other users, and going through
all the steps above.

That should give you a good start on integrating GitHub into your
current projects and using it to keep your code organized and
working even while it is being extended and improved.  We'll
also look very quickly at how documentation can be incorporated.
