---
description: What to do when creating a new WWT GitBook document.
---

Here are some miscellaneous notes about creating new documents in [GitBook].

[GitBook]: https://docs.gitbook.com/

## “Official” documents

Anyone can create a repository on GitHub and an account on GitBook, so anyone
can follow these guidelines. However, “official” WWT documents are
distinguished by two characteristics:

1. The Git source repository is hosted in the
   [WorldWideTelescope GitHub organization](https://github.com/WorldWideTelescope).
2. The rendered GitBook book is hosted in the [@worldwidetelescope] GitBook
   organization.

[@worldwidetelescope]: https://app.gitbook.com/@worldwidetelescope/spaces

To create a new official WWT document, will need to be a member of these
organizations, or to obtain the assistance of someone who is.

{% hint style="warning" %}
Free GitBook accounts only let you create one public document. If you’d like
to write more than one, talk to the WWT team about adopting your first
document to allow you to create a second.
{% endhint %}


## Step 1: Stub out your document

The first step is to stub out your document in a new Git repository. Use
[the wwtdoc-misc repository](https://github.com/WorldWideTelescope/wwtdoc-misc/)
as a template, setting up the file structure as described in the
[repository structure](./repo-structure.md) page.


## Step 2: Link your document up to GitBook

In your GitBook organization, such as [@worldwidetelescope], create a new
“space”, filling in a user-facing title.

Once the space has been created, there are a few setup steps:

1. In the “Advanced” settings (the icon looks like horizontal sliders), edit
   the “Space URL” to make it terser if necessary. For an official document,
   the URL will have the form
   `https://worldwidetelescope.gitbook.com/spacename`, so any extra components
   alluding to WWT are not necessary.
2. In the “Integrations” settings (the icon is a cube viewed from an angle),
   turn on GitHub and link the space up to your repository. Only render the
   master branch, and specify that the document will be authored on Git*Hub*,
   not Git*Book*.
3. Once the GitHub integration is turned on, re-open that panel and turn on
   “Display the Button”.
4. In the “Customization” settings (the icon is a paint roller), go to “Pages”
   and turn off the “Page Rating” feature. We don’t want to ask people to
   provide information that we’re going to ignore, and at this juncture it is
   extremely implausible that we’re going to look at that rating information.

Once the GitHub integration has been set up, your document should be viewable
in its rendered form! The shareable link to the rendered document can be found
in the GitBook “Share” settings panel (the icon is an up arrow emerging from a
box).


## Step 3: Add your document to the Contributors’ Hub

The [WWT Contributors’ Hub] contains a list of WWT-related documents. Open a
pull request against
[its backing repository](https://github.com/WorldWideTelescope/worldwidetelescope.github.io/)
to add your new document to the list!

[WWT Contributors’ Hub]: https://worldwidetelescope.github.io/
