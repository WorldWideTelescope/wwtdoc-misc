---
description: "Setting up a Windows virtual machine for WWT development."
---

WWT originated as an application for Microsoft Windows and much of its
infrastructure is still very Windows-centric. Most astronomers, on the other
hand, use macOS or Linux. This document gives a recipe for setting up *free,
legal* Windows virtual machine (VM) that can be used for WWT software
development.

Unfortunately, Windows is very unfriendly to automation, so the paradigm we
use here is to set up a VM that you interact with graphically, rather than say
a system based on [Vagrant]. It would be great to have something headless, or
just more automatable, but we haven’t been able to put the pieces together
just yet.

[Vagrant]: https://www.vagrantup.com/


# Preliminaries

One of the costs of using VMs is that they are pretty hungry for disk space.
We recommend that you have *80 GiB* of disk space free for the process of
setting up your VM. Once it’s running, you'll only need about half that.

You need VM software installed on your main computer (the ”host machine”), of
course. [VirtualBox] is known to work well. However, nothing here is very
specific to the particular VM system that you’re using, so things should be
quite portable to other systems if you’re not using VirtualBox.

[VirtualBox]: https://www.virtualbox.org/

You’ll also need a Microsoft account in order to install the developer tools.
Have your login information handy.


# Downloading and install the base VM

The key is that nowadays Microsoft makes Windows VM images available freely.
Here is the magic link:

https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/

Choose the “MSEdge on Win10” option and the platform that works for you;
current options are VirtualBox, Vagrant, VMWAre, HyperV, and Parallels. Begin
the download! It will probably take a while.

The Microsoft page makes a big point about how the VMs expire after 90 days.
In my experience, it seems that you can pretty much just keep on using them
after the 90-day limit. But it is probably prudent to expect that you might
have to rebuild your WWT dev VM every three months.

Once the file is downloaded, do whatever you need to create a new VM instance
based on it. This process should hopefully be straightforward.

Boot up your shiny new VM. The default screen is not very helpful, but if you
press the `Esc` key, you should get a prompt to log in as the user `IEUser`.
The universal password is `Passw0rd!`.


# Set up the software environment

This is the most annoying part.

1. In the “Type here to search” box, type in “update”, and click the “Check
   for updates” choice when it eventually appears. Let Windows install its OS
   updates, and reboot if/when needed. Check for more updates — some can only
   be installed after earlier updates have been applied. Repeat until the VM is
   fully up-to-date.
2. Install Google Chrome, the recommended WWT web browser. Open up IE Edge, go
   to <https://www.google.com/chrome/>, and follow the instructions. Make it
   your default browser. Sorry, IE.
3. If you use a password manager such as LastPass, it might be helpful to
   install it now.
4. We find it very useful to have a lightweight, standalone text editor
   installed. There are several options, but Notepad++,
   <https://notepad-plus-plus.org/>, seems to be a good option. Note that
   [Atom](https://atom.io/) is a large install can seriously hamper your
   ability to fit everything you need in the 40 GiB drive allocated to the VM.
5. The “Git Bash” tool, combining Git with a bash shell and core utilities, is
   also extremely helpful. Download and install it from
   <https://git-scm.com/download/win> — note that it is just referred to as
   “Git”, not “Git Bash”. Default options are generally OK, but you’ll
   probably want to select Notepad++ as your text editor.
6. Now, the big one: Visual Studio.
   1. Search for “visual studio install older version” and find the result
      that seems most on-point.
   2. Select to download Visual Studio 2015. You’ll need to sign in to a
      Microsoft account to do so.
   3. Find, download, and launch “Visual Studio Community 2015 with Update 3”.
   4. Choose a Custom install.
   5. Click through the component selection — it should just be the “Web
      developer” tools and nothing else extra.
