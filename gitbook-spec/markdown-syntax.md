---
description: Summarizes GitBook’s enhanced Markdown syntax
---

# GitBook Enhanced Markdown Syntax

[GitBook] documents are generally expressed in [Markdown] syntax, but GitBook
implements several extensions that aren’t necessarily documented clearly. This
page offers a quick reference.

[GitBook]: https://docs.gitbook.com/
[Markdown]: https://www.markdownguide.org/

{% hint style="info" %}
This document does *not* aim to be a general guide to Markdown. If you need
general Markdown help, there are dozens of tutorials and cheat sheets a web
search away.
{% endhint %}


## Metadata Stanza

GitBook Markdown files can start with a metadata stanza having a typical form:

```
---
description: The page’s description
---
```

This is probably [YAML] syntax but I’m not 100% sure about that.

[YAML]: https://yaml.org/

The only key that I know about is the one shown above, `description`. It
provides a short description of the page that will be shown at its top.


## Admonishments

You can include “admonishment” paragraphs that are called out in a special
box. Sample syntax is:

```
{% hint style="info" %}
This is an informational admonishment.
{% endhint %}
```

The allowed styles are `info`, `tip`, `danger`, and `working`. Here’s an info
admonishment:

{% hint style="info" %}
This is an informational admonishment.
{% endhint %}

And here’s `tip`:

{% hint style="tip" %}
This is an tip.
{% endhint %}

And here’s `danger`:

{% hint style="danger" %}
Danger Zone!
{% endhint %}

And here’s `working`:

{% hint style="working" %}
Did they mean “warning”?
{% endhint %}


## Code Samples

Standard Markdown code blocks, delimited in triple backticks, work just fine.
They get styled like this:

```python
print('Python sample')
```

You can use a language tag to tell GitBook to apply syntax highlighting for a
particular language; above, I used the word `python` immediately after the
opening backticks.

*Document rest here*


## HTML

According to
[the relevant GitBook docs](https://docs.gitbook.com/integrations/github/limitations#html),
arbitrary HTML content in your Markdown will not be honored.
