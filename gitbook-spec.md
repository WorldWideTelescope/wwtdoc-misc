# GitBook MarkDown Format Specification

WWT uses [GitBook] to render and host most of its documentation. The way we
use it, documents are written using [Markdown] syntax and version-controlled
in Git repositories on [GitHub]. GitBook monitors these repositories and
updates the published versions when updates are pushed to the `master` branch.

It appears that GitBook is currently emphasizing a different authoring model,
in which you write documents on their website using a graphical interface. We
don’t favor that model because it doesn’t offer a clear pathway for external
contributors to get involved. Because of this emphasis, though, GitBook
doesn’t really describe the extensions to Markdown syntax that they offer!
This document describes how our GitBook document repositories should be
structured and the Markdown syntax that can be used.

[GitBook]: https://docs.gitbook.com/
[Markdown]: https://www.markdownguide.org/
[GitHub]: https://github.com/WorldWideTelescope/
