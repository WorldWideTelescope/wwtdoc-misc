---
description: The file structure for WWT GitBook documentation repositories.
---

[WWT] [GitBook] documentation repositories should contain at least the four
following files at the top level:

- `README.md`
- `.gitbook.yaml`
- `index.md`
- `SUMMARY.md`

[WWT]: http://www.worldwidetelescope.org/
[GitBook]: https://docs.gitbook.com/


## README.md

By default, in [GitBook], this file is the main page of the document. However,
this gets confusing for people who visit the GitHub source repository for a
document, because they just see a somewhat-mangled version of the actual
document. We’d like to offer such people some explanatory text explaining that
they’re looking at the source repository for a piece of WWT documentation.
Fortunately, the `.gitbook.yaml` makes it possible to do so.

So for WWT document repositories, `README.md` should offer exactly this kind
of explanation. Use
[the README associated with the `wwtdoc-misc` repository](https://raw.githubusercontent.com/WorldWideTelescope/wwtdoc-misc/master/README.md)
as a template.


# .gitbook.yaml

Configuration specific to [GitBook] is stored here. Once again, use
[the YAML file associated with the `wwtdoc-misc` repository](https://github.com/WorldWideTelescope/wwtdoc-misc/blob/master/.gitbook.yaml)
as a template.

The content should look something like this:

```
root: ./

structure:
  readme: index.md
  summary: SUMMARY.md
```

See
[the relevant GitBook documentation](https://docs.gitbook.com/integrations/github/content-configuration)
for more details.


# index.md

This is the landing page of your document. It should follow the same general
structure as every other document page, described
[on the next page](./markdown-syntax.md).


# SUMMARY.md

This specifies the table of contents of your book. It follows a special format
[documented on GitBook](https://docs.gitbook.com/integrations/github/content-configuration#summary).
Here’s a template, showing WWT’s recommended file structure:

```
# Summary

## Use headings to create page groups like this one

* [First page's title](page1.md)
  * [Some child page](page1/child1.md)
  * [Some other child page](part1/child2.md)
* [Second page's title](page2.md)

## A second page group

* [Yet another page](another-page.md)
```

The titles that you use in this file will be the ones shown at the top of each
respective page.

Also note that “page group” names will enter into your URLs. For instance, the
[“miscellaneous documentation”](https://github.com/WorldWideTelescope/wwtdoc-misc/)
repository that contains this specification
[groups documents under a “Documents” group](https://github.com/WorldWideTelescope/wwtdoc-misc/blob/master/SUMMARY.md),
so that the URL to this page is
<https://worldwidetelescope.gitbook.io/miscellaneous/documents/gitbook-spec/repo-structure>.
