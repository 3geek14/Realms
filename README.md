# Realms #

This repository maintains the Realms Omnibus, and is primarily used by the
Omnibus Editorial Committee. If you happen to prefer git pull requests over the
proposal system on the Realms website, Pi is willing to convert pull requests
from here into proposals on [RealmsNet](https://www.realmsnet.net/). Please do
not assume your pull requests will be merged if you aren't on the OEC; they will
most likely be closed.

# Guides #

This version of the Omnibus is written in Markdown. Please read the [Markdown
tutorial](https://3geek14.github.io/Realms/MarkdownTutorial) to learn how to use
Markdown. If you already know Markdown, please read the tutorial so that the
code is consistent.

To convert from Markdown to HTML, we use Pandoc. [Pandoc's
website](http://www.pandoc.org/installing.html) has installation instructions.
Please use version 2.6, which is the most recent version, so that you have the
same version as everyone else. Once installed, you can compile a new version of
the Omnibus with the command:

    pandoc -o Omnibus.html -s -c pandoc.css Omnibus.md

This project is maintained with git on GitHub. There are many [GitHub
tutorials](https://guides.github.com/activities/hello-world/) available. Please
read one of those, and then go over our [editing
procedures](https://3geek14.github.io/Realms/EditingProcedures) document.