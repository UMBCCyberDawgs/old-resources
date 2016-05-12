---
title: Gathering Your Tools
type: homepage
authors:
  - Zack Orndorff
---

## Getting Started

Before you can actually start learning about security stuff, you'll need some
tools to get started. Fortunately, all the basic (and many advanced) tools
are free.

## Virtualization: VirtualBox

In studying security, we need to be able to try many different things out, and
we usually want to avoid messing up our computers. The easiest way to do that is
to do our practice in virtual machines or VMs. The easiest/cheapest way to do
that is with a piece of software called VirtualBox, which can be downloaded for
free from [Oracle's VirtualBox site][virtualbox].

Other popular virtualization programs include VMWare, Xen, Hyper-V, and KVM, if
you were to want to do more research. However, most of those are aimed primarily at
servers.

### Getting some VMs

Once you've installed that, you'll want an operating system to run inside your
VM. A VM without an operating system is just like a normal computer without an
operating system: it doesn't do anything.

#### Kali Linux

So for security-specific work, you'll want to start with Kali Linux. It's far
from perfect, but it's a great start because it comes with almost all the tools
you'll need already installed (or easily available). For instance, most
competitions we participate in seem to assume you have the tools that come with
Kali. You could try to install them one at a time, but its easiest to use Kali.

You could install it manually, but to try it out, you can use a pre-made VM. You
can download it from the Offensive Security website: [Kali Linux Custom Images
Download][offensive-security-kali]. (You'll want the 64-bit one for VirtualBox,
unless your computer is only 32-bit.)

You'll need 7-zip to unzip that pre-made VM, which you can download from [the
7-zip site][7zip].

Unzipping the VM will give you a .ova file, which you can import into VirtualBox
by doing File > Import Appliance.

I'll recommend starting with that, but keep in mind it's good for security
practice, not general Linux practice. Particularly of note is that it has you
logging in as root, which is *reasonably okay* to do in Kali, but you should
**absolutely not** log in directly as root otherwise. (You should instead log
in as a regular user and then use something like `su` or use `sudo`)

#### Optional: Ubuntu Linux or CentOS Linux

**Optional**: So this is optional, but if you want to do more-normal Linux
practice, you can install another Linux distribution in another VM. (That's the
beauty of VMs -- you can have more than one at a time.)

We'd suggest either Ubuntu or CentOS to start. Both are popular choices for
servers in the real world.

You can download Ubuntu from the [Ubuntu download page][ubuntu-download]. You'll
want the latest 64-bit server version (unless you have an old computer that only
supports 32-bit).

You can download CentOS from the [CentOS download page][centos-download]. You'll
want the latest 64-bit server version (unless you have an old computer that only
supports 32-bit). I suggest either the DVD ISO or the Minimal ISO (but the
Minimal ISO will require the network to install, the DVD ISO will not).

##### Creating a VM from an ISO

Those downloads will give you ISO images of DVDs. You need to then install them.
VirtualBox has documentation of [how to create a new VM][vbox-createvm]. As for
actually installing the OS, you can give it a shot, Google around for a
tutorial, or ask somebody; it's fairly straightforward once you get started.

## More coming soon?

That's really it, anything else you need can most likely be installed easily
within a VM using either Apt or Yum (the Linux package managers).

We'll likely come up with something else to put here later.

I guess if you're using Internet Explorer for some reason, as a matter of
practice you should probably install Chrome or Firefox?

[virtualbox]: https://www.virtualbox.org/wiki/Downloads
[offensive-security-kali]: https://www.offensive-security.com/kali-linux-vmware-virtualbox-image-download/
[7zip]: http://www.7-zip.org/
[ubuntu-download]: http://www.ubuntu.com/download/server
[centos-download]: https://www.centos.org/download/
[vbox-createvm]: https://www.virtualbox.org/manual/ch01.html#gui-createvm
