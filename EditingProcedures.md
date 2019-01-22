% Editing Procedures

[Index](https://3geek14.github.io/Realms/)

# Using git on the OEC #

After the EHC, once the OEC has been elected, it is time to start working on the
new year's Omnibus. The first step is to go through the previous year's Omnibus
to remove all indicators that text is new (red underlines). Hopefully, Pi will
have already done this, along with making a new branch named with the year (e.g.
`2019` for the 2019 Omnibus). Remember that [red text]{.new} is written as:

    [red text]{.new}

## Implementing Changes ##

The second step is to start making changes. There are two types of changes the
OEC can make. The first is implementing proposals that were submitted; the other
is editorial changes, such as grammar and formatting.

Download the most recent version of the Omnibus, pick a change nobody else is
working on yet, and start implementing the change!

When you finish implementing something, compile the file with Pandoc and make
sure everything looks right. Remember, the
[index](https://3geek14.github.io/Realms/) has the command to use to compile,
and you can find installation instructions for Pandoc from there. Then `commit`
the change to a new branch. To keep things consistent, please follow the
following naming scheme for the name of your new branch:

* For proposals, name the branch `proposal/`, followed by the name of the
  proposal on RealmsNet, removing all punctuation, making letters lowercase, and
  replacing spaces with hyphens. For example, if there's a proposal named "New
  Spell: Power Creep", the branch would be named
  `proposal/new-spell-power-creep`.
* For other changes, name the branch `editorial/`, followed by the section in
  the Omnibus, and then followed by some description of the change. For example,
  if someone thought the grammar in Embrace Death needed to be fixed, they could
  name the branch `editorial/6.6/grammar-in-embrace-death`, because the spell
  descriptions are in section 6.6.

You can also do that before you quite finish simply as a way to save your work,
and to let other people know you've started working on that change (so they can
focus on other changes). When you finish, double-check your work. If text has
been added, it should have a red underline. After you've double-checked, open a
pull request to merge from your branch into the branch for the new Omnibus. That
signals to everyone else that you think your change is ready to be put into the
official version.

## Reviewing Changes ##

The third step is to review other people's changes. Of course, this doesn't have
to wait until all the changes are implemented, and it's probably better to swap
between the two. As other people on the team make edits, they'll be making pull
requests. These can't be merged into the final version until they've been
reviewed. Because there are five members of the OEC, and at least a majority
should see each change to make sure it's correct, each pull request needs two
approvals before it can be merged.

To review a pull request, first get that branch onto your computer. Then compile
the markdown into HTML, just to make sure the HTML file is up-to-date. GitHub
will show you what changed in each file from the pull request's page, so you can
look at that to see where you should look in the HTML file for changes. Remember
to check that all added text is marked as new, is spelled correctly, and
implements the change that it should. If everything looks good, approve the pull
request. If you're the second person approving, you can then merge it. (One
person submitted the pull request and two other people approved, so a majority
support the change.)

## Merge Conflicts ##

As much as we would like this to not be the case, sometimes two changes will
conflict with each other. Why does this happen? Suppose two people both start
making changes to the same section. One of them is implementing a proposal that
rearranges things, and the other is making editorial changes to fix spelling and
grammar. They both make pull requests and get approvals. The first one gets
merged, and it goes well. The second one is now making changes to sentences that
are no longer in the original place. Git isn't quite good enough to understand
things this complicated, so GitHub will show that there's a merge conflict, and
the pull request won't be able to be merged.

When this happens, the pull request with a conflict will need another commit to
resolve the conflict. Preferably, whoever opened the pull request will do this.
After a new commit has been added, approvals will go away. If the same person
who opened the pull request is the person who fixes the merge conflict, two
more people approving after that will make sure that three people have seen the
change. That said, if that person is busy, someone else can make the change, but
then they should not be one of the two reviewers.