These are just my git scripts that I've come up with over the years to make things easier
and to remind me how to do stuff that I'm always forgetting.

It's old, so some of this might have been already added to git core, let me know.

The ones I use frequently:

#### git up

<code>git-simpull</code> is my usual method of pulling from origin – I have it symlinked as <code>git up</code>.

It does a <code>stash</code>, then a <code>pull --rebase</code>, then a <code>stash pop</code> (if everything goes well).

If the rebase fails, you still have to handle it yourself. I'd like to add some kind of intelligence to be able
to run this again to clean up after itself, but for now, you can use <code>git recon</code> to continue the rebase and apply the stash.


#### git list

This is a compact form of <code>git log</code> that I prefer because it doesn't take over my whole terminal window
with a bunch of irrelevant stuff.

You can do

    git list 30

to show 30 commits if you need a longer list, and

    git list brunch

to list the brunch branch, or some other rev.

I make a .mailmap file for each of my repos that abbreviates all the contributors names to a standand number of characters, 4 or 5 (using nbsp  as padding).
This keeps the output of git-list nice and columnar.


#### git enstage

I alias this as <code>git a</code> and use it instead of <code>add</code>. I got tired of adding each file individually and
following up with <code>git status</code> to check my work, so <code>git a</code> adds all of its arguments with the <code>--all</code> option
and then does a <code>git status</code>.


#### git addap

A wrapper around <code>git add -p</code> that also prompts to add changes in unstaged files, provided there aren't more than 8 of them
and they aren't more than 300 lines. I alias it as <code>git ap</code> and use it instead of <code>git a</code> when I want to see what
changes I'm staging or only stage some changes.


#### git timewarp

Did you forget to commit yesterday and want your git record to show when you actually did this work?

    git timewarp 15 hours ago

will make a commit with a modified timestamp. Magic.
