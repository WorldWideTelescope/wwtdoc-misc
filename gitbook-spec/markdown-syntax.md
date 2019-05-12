---
description: GitBook’s enhanced Markdown syntax.
---

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

The enhancements documented here are:

- [The metadata stanza](#metadata-stanza)
- [Leadoff titles are ignored](#leadoff-titles-are-ignored)
- [Internal links](#internal-links)
- [Admonishments](#admonishments)
- [Code samples](#code-samples)
- [Generic tab boxes](#generic-tab-boxes)
- [Display math](#display-math)
- [Checklists](#checklists)
- [Downloadable files](#downloadable-files)
- [Web API method styling](#web-api-method-styling)
- [Explicit HTML is ignored](#explicit-html-is-ignored)
- [Definition lists are not available](#definition-lists-are-not-available)


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


## Leadoff titles are ignored

If you begin your document with a heading à la

```
# This is my title
```

it will be ignored. The title displayed at the top of each page comes from the
[SUMMARY.md](./repo-structure.md#summary-md) file.


## Internal Links

To make an internal link, make a link beginning with `./` and pointing to
the name of a Markdown file in the repository. Paths are relative to the
current document; for instance, to link to the previous page, I can write:

```
[a link like this](./repo-structure.md)
```

(which generates [a link like this](./repo-structure.md)), rather than having
the link text be `./gitbook-spec/repo-structure.md`.

Other forms might work, but I haven’t tried!

You can also write a page reference that is called out fairly aggressively
like so:

```
{% page-ref page="../index.md" %}
```

This gets rendered as:

{% page-ref page="../index.md" %}

Once again, the file path is relative to the current Markdown file’s location
in the Git repository.


## Admonishments

You can include “admonishment” paragraphs that are called out in a special
box. Sample syntax is:

```
{% hint style="info" %}
This is an informational admonishment.
{% endhint %}
```

The styles are `info`, `success`, `warning`, and `danger`. Here’s an info admonishment:

{% hint style="info" %}
This is an informational admonishment.
{% endhint %}

And here’s `success`:

{% hint style="success" %}
Good job, you did it!
{% endhint %}

And here’s `warning`:

{% hint style="warning" %}
Something might go wrong.
{% endhint %}

And here’s `danger`:

{% hint style="danger" %}
Danger Zone!
{% endhint %}


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


## Generic Tab Boxes

You can create generic boxes with tabbed content that the viewer can choose
between:

```
{% tabs %}
{% tab title="First Tab" %}
Here is first tab content.
{% endtab %}

{% tab title="Second Tab" %}
Here is second tab content.
{% endtab %}
{% endtabs %}
```

Which gets rendered as:

{% tabs %}
{% tab title="First Tab" %}
Here is first tab content.
{% endtab %}

{% tab title="Second Tab" %}
Here is second tab content.
{% endtab %}
{% endtabs %}

Again, however, we do not recommend using this feature since it can be
confusing.


## Display Math

GitBook supports display equations compiled with LaTeX! Just encase them in
double dollas as you would in a LaTeX document:

```
$$
e^{\pi i} + 1 = 0
$$
```

Becomes:

$$
e^{\pi i} + 1 = 0
$$

Nice!


## Checklists

You can make checklists in the same way as on GitHub:

```
- [x] Completed item.
- [ ] This item has not been completed.
```

Which gets rendered as:

- [x] Completed item.
- [ ] This item has not been completed.


## Downloadable Files

You can include a link to downloadable file by adding it to your repository
and using the following markup:

```
{% file src="sample-downloadable-file.txt" %}
```

This will get rendered like this:

{% file src="sample-downloadable-file.txt" %}

As with other internal links, the path to the file in question is relative to
that of the Markdown file currently being processed in the repository. In this
case, the file’s location relative to the repository root is
[gitbook-spec/sample-downloadable-file.txt](https://github.com/WorldWideTelescope/wwtdoc-misc/blob/master/gitbook-spec/sample-downloadable-file.txt).


## Web API Method Styling

GitBook provides a fairly elaborate framework for document Web API methods.
The interactive entry form is documented
[here](https://docs.gitbook.com/content-editing/rich-content#api-methods).
However, the structured used here is highly tuned towards modern web APIs that
are unlike WWT’s, so we don’t expect the special syntax to be very useful in
the WWT context. For reference, here is *a subset* of the special tags used in
the Markdown representation of this construct:

```
{% api-method method="get" host="https://api.example.com" path="/urlpath/:param" %}
{% api-method-summary %}
method-name
{% endapi-method-summary %}

{% api-method-description %}
Method description.
{% endapi-method-description %}

{% api-method-spec %}
(A lot of additional markup goes here, but I have not documented it since
I don't think we'll be using this construct.)
{% endapi-method-spec %}
{% endapi-method %}
```

Which results in:

{% api-method method="get" host="https://api.example.com" path="/urlpath/:param" %}
{% api-method-summary %}
method-name
{% endapi-method-summary %}

{% api-method-description %}
Method description.
{% endapi-method-description %}

{% api-method-spec %}
(A lot of additional markup goes here, but I have not documented it since
I don't think we'll be using this construct.)
{% endapi-method-spec %}
{% endapi-method %}


## Explicit HTML is Ignored

According to
[the relevant GitBook docs](https://docs.gitbook.com/integrations/github/limitations#html),
arbitrary HTML content in your Markdown will not be honored.


## Definition Lists are Not Available

Unfortunately, there seems to be no mechanism to express a [definition list],
also known as a “description list”. Try a table instead:

```
| Name | Description |
| :-- |
| First | This is the first. |
| Second | This is the second. |
```

[definition list]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl
