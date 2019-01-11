# Realms #

To compile a new version of Omnibus.html locally, run

    pandoc -o Omnibus.html -s -c pandoc.css Omnibus.md

## Tutorial ##

View this page [here](https://3geek14.github.io/Realms/) for better formatting.

Markdown is one of the simpler languages to use for formatting text. Because
we're tracking things in git, we're using plaintext, so we need to use some
language to specify the formatting. One of the design goals of markdown is to
match what people would normally do in plaintext, which is a large factor for
why I picked it. For example, underscores around text are used for emphasis.

    _This is italics._ __This is bold.__

::: {.example}
_This is italics._ __This is bold.__
:::

You might find tutorials online with other ways to emphasize things, such as
with asterisks. Markdown has a lot of features we won't use, so this guide will
only show you some ways of doing certain things that can be done in other ways.
For the sake of consistency, please try to use the same methods shown here.

There are many different types of markdown. The specific one we're using is
Pandoc's version of markdown. Pandoc is a tool designed to convert between a lot
of different formats, and its version of markdown has basically everything we
want to use for the Omnibus. GitHub has its own version, which is very similar,
but it's missing a couple things (which is why you should be viewing this page
[here](https://3geek14.github.io/Realms/), if you weren't already).

As with many plaintext formats, a blank line is needed to create a new
paragraph. The reason that a single new line won't create a new paragraph is so
that we have the option to keep individual lines of code shorter. This isn't
strictly necessary, but it does make it a little easier to see what changed
using git's tool for showing differences between versions (called `diff`). As an
example of this:

    This is one long paragraph
    that's super long. So long
    that whoever wrote it wanted
    to split it up amongst a
    bunch of different lines.
    
    This is a new paragraph.

::: {.example}
This is one long paragraph
that's super long. So long
that whoever wrote it wanted
to split it up amongst a
bunch of different lines.

This is a new paragraph.
:::

As a rough guideline, try to keep lines of code no longer than 80 characters.
Don't worry too much about this, as things will change when text is made red or
black. It's a guideline, and we trust each other to use good judgement.

### Headings ###

There are three levels of headings we use in the Omnibus. Section numbers are
the biggest, subsection numbers are next, and then come things that aren't
numbered. Here are some examples from the Omnibus:

    # 1: General Player Information #
    
    ## 1.3: How Do I Start Playing? ##
    
    ### Realms Events ###

::: {.example}
# 1: General Player Information #

## 1.3: How Do I Start Playing? ##

### Realms Events ###
:::

If you're familiar with HTML, these correspond with `h1`, `h2`, and `h3` tags.
The first heading is the most important, so it's biggest. If you look at the
code so far, you'll see headings are done a little bit differently. They have
something extra at the end:

    # 1: General Player Information # {#general-player-information}

::: {.example}
# 1: General Player Information # {#general-player-information}
:::

The point of this is so we can put in links to specific parts of the document.
Markdown will automatically do this for headings, but it won't always pick quite
the same name that we would pick. Also, specifying it makes it easier to copy
and paste.

Speaking of links, how do we make them? There are two parts: the text that
should direct to somewhere else, and the place it points to (the target).
Headings are given targets as shown above, but we can make other things targets
as well.

    [This is a link target]{#my-link-target}
    
    This is a [link](#my-link-target) to a target.
    
    This is a [link](https://www.realmsnet.net/) to RealmsNet.
    
    This is an email address: <arbitration@lists.realmsnet.net>.

::: {.example}
[This is a link target]{#my-link-target}

This is a [link](#my-link-target) to a target.

This is a [link](https://www.realmsnet.net/) to RealmsNet.

This is an email address: <arbitration@lists.realmsnet.net>.
:::

To make a link target, use curly braces (`{}`). To navigate to a link, use
parentheses (`()`). Email addresses are a little different; they use less than
and greater than (`<>`).

Tables are kind of messy. It's not super easy to make a table in plaintext, and
it usually comes out looking pretty bulky. The table's we're using are called
grid tables, because we draw a grid in the code. Yes, things have to line up for
it to work. If you're having trouble getting a table to work, feel free to make
me do it, because I'm the one who picked markdown. Of course, the OEC is allowed
to reformat things, so if you think of a way to present the same information
without a table, feel free to try it out.

    +----------+----------+------------------------+
    | Column 1 | Column 2 | Wider Column           |
    +==========+==========+========================+
    | apple    | banana   | lots of text           |
    |          |          | that doesn't           |
    |          |          | fit on one             |
    |          |          | row of code            |
    +----------+----------+------------------------+
    | text\    | ugh      | tables suck            |
    | with an  |          |                        |
    | explicit |          |                        |
    | line     |          |                        |
    | break    |          |                        |
    +----------+----------+------------------------+

And let's look at what that turns into.

::: {.example}
+----------+----------+------------------------+
| Column 1 | Column 2 | Wider Column           |
+==========+==========+========================+
| apple    | banana   | lots of text           |
|          |          | that doesn't           |
|          |          | fit on one             |
|          |          | row of code            |
+----------+----------+------------------------+
| text\    | ugh      | tables suck            |
| with an  |          |                        |
| explicit |          |                        |
| line     |          |                        |
| break    |          |                        |
+----------+----------+------------------------+

:::

So yeah, tables kind of suck. The relative widths of the columns in the code
becomes the relative widths of the columns in the result. If the table doesn't
use the top row as labels, replace the equals signs (`=`) with hyphens (`-`).

Column alignment is done by placing colons on the row with equals signs (or the
top row, if there's header row).

    +------+-------+--------+
    | Left | Right | Center |
    +:=====+======:+:======:+
    | left | right | center |
    +------+-------+--------+
    
    +:-----+------:+:------:+
    | Left | Right | Center |
    +------+-------+--------+
    | left | right | center |
    +------+-------+--------+

::: {.example}
+------+-------+--------+
| Left | Right | Center |
+:=====+======:+:======:+
| left | right | center |
+------+-------+--------+

+:-----+------:+:------:+
| Left | Right | Center |
+------+-------+--------+
| left | right | center |
+------+-------+--------+

:::

Next come lists. There are three different types of lists we use in the Omnibus.
The first is bulleted lists, which is most common. Begin each item with an
asterisk (`*`), and make sure there's an empty line before the list.

    * This is the first list item.
    * This is the next one.
    * This on has enough text to be
      multiple lines of code.
    * This is another list item.

::: {.example}
* This is the first list item.
* This is the next one.
* This on has enough text to be
  multiple lines of code.
* This is another list item.
:::

We also use numbered lists. We so far only use this for the rules we play and
fight by. For numbered lists, specify the number for the first item, and then
use the number symbol (`#`) for later items.

    1. This is the first item.
    #. This is the second item.
    #. Notice the period after the number.
    
    Put some text in to separate the lists.
    
    11. This is a new list beginning with 11.
    #.  Notice that there's an extra space now
        to keep things aligned.

::: {.example}
1. This is the first item.
#. This is the second item.
#. Notice the period after the number.

Put some text in to separate the lists.

11. This is a new list beginning with 11.
#.  Notice that there's an extra space now
    to keep things aligned.
:::

Finally we have soemthing called a description list. The idea behind this is for
lists where you want to name each item rather than numbering them. Sure, you
could use a bulleted list and start each one with some bold text, but this way
looks more _classy_. There are some places we don't use these where we probably
should.

    Italics
    : Use a single underscore around text
      to make it italics, like _this_.
    
    Bold
    : Use double underscores around text
      to make it bold, like __this__.
    
    Description Lists
    : Put the name of something on one
      line, then put the description on
      the next line. The first line of
      the description should begin with a
      colon, and all the lines of the
      description should line up. Start
      new descriptions with a blank line
      before them.

::: {.example}
Italics
: Use a single underscore around text
  to make it italics, like _this_.

Bold
: Use double underscores around text
  to make it bold, like __this__.

Description Lists
: Put the name of something on one
  line, then put the description on
  the next line. The first line of
  the description should begin with a
  colon, and all the lines of the
  description should line up. Start
  new descriptions with a blank line
  before them.
:::

You can also nest lists. This currently only comes up in the Undeath part of
Basic Magic Effects Everyone Should Know, I think.

    * This is the main list.
    * This list has bullet points.
    * This item has a sub list.
      * This bullet point will look
        different.
      * Because this is a sub list.
    * This item has a numbered sub list.
      5. For some reason, this sublist
         starts at five.
      #. No good reason, other than to
         show it can be done.
      #. Let's go deeper, shall we?
         * Sub sub lists never indicate
           anything bad, right? They're
           super clear.
    * This is the final item.

::: {.example}
* This is the main list.
* This list has bullet points.
* This item has a sub list.
  * This bullet point will look
    different.
  * Because this is a sub list.
* This item has a numbered sub list.
  5. For some reason, this sublist
     starts at five.
  #. No good reason, other than to
     show it can be done.
  #. Let's go deeper, shall we?
     * Sub sub lists never indicate
       anything bad, right? They're
       super clear.
* This is the final item.
:::

One final thing about markdown. We need to have a way to specify text that was
added this year. The way to do this looks very similar to a link target. The
reason for this is that the HTML is very similar. To make something red, we
label it as `new`. We do this as follows:

    [This sentence is new.]{.new}
    This sentence is old. This
    sentence had something
    [changed]{.new}.

::: {.example}
[This sentence is new.]{.new}
This sentence is old. This
sentence had something
[changed]{.new}.
:::

Technically, this doesn't do anything by itself. However, there's a CSS document
in the github repository that will look for anything called `.new`, and it'll
give that a red underline. This is something that we have the authority to
change, since it's formatting. Also, I don't see anything in the Omnibus that
specifies that we need to do this, but it's a long-standing convention to label
what's new. The reason I chose to do this instead of red text is simply because
links are blue, and I think this makes it easier to see what's going on when
there's new text that has a link.