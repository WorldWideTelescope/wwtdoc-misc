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

The important styles are `info` and `danger`. Here’s an info admonishment:

{% hint style="info" %}
This is an informational admonishment.
{% endhint %}

And here’s `danger`:

{% hint style="danger" %}
Danger Zone!
{% endhint %}

There are also `tip` and `working`, but last I checked, they gave the same
results as `info`.


## Code Samples

Standard Markdown
[fenced code blocks](https://help.github.com/en/articles/creating-and-highlighting-code-blocks),
delimited in triple backticks, work just fine. They get styled like this:

```python
print('Python sample')
```

You can use a
[language identifier](https://help.github.com/en/articles/creating-and-highlighting-code-blocks#syntax-highlighting)
to tell GitBook to apply syntax highlighting for a particular language; above,
I used the word `python` immediately after the opening backticks.

But you can also use an extended syntax that lets you show example code
associated with a specific filename, and multiple tabs that the viewer can
choose between. The syntax is:

    {% code-tabs %}
    {% code-tabs-item title="myfile.py" %}
    ```python
    print('Here is a nice Python code block.')
    ```
    {% endcode-tabs-item %}
    {% code-tabs-item title="myfile.js" %}
    ```js
    console.log('Here is some JavaScript.');
    ```
    {% endcode-tabs-item %}
    {% endcode-tabs %}

This gets rendered as:

{% code-tabs %}
{% code-tabs-item title="myfile.py" %}
```python
print('Here is a nice Python code block.')
```
{% endcode-tabs-item %}
{% code-tabs-item title="myfile.js" %}
```js
console.log('Here is some JavaScript.');
```
{% endcode-tabs-item %}
{% endcode-tabs %}

We do *not* recommend using the “tabs” feature, however, since it can be
confusing if people don’t realize that there are different pieces of code
associated with the different tabs.


## HTML

According to
[the relevant GitBook docs](https://docs.gitbook.com/integrations/github/limitations#html),
arbitrary HTML content in your Markdown will not be honored.
