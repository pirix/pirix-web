---
title: Building Pirix
layout: default
---

# Building Pirix

This is a guide on how to build Pirix from source. The build process is very simple but compiling the toolchain will take some time, especially on slower processors.

## Requirements

Pirix should build on every POSIX-compatible operating system, but the build
process has only been tested on Linux and Mac OS by now. You will need the
following software:

- [**GCC**](http://gcc.gnu.org/), the GNU Compiler Collection
- [**SCons**](http://www.scons.org/), a Makefile alternative written in Python

## Toolchain

To make the process of building the toolchain much simpler there are
scripts which apply the patches and compile everything:

{% highlight bash %}
$ git clone git://github.com/pirix/pirix-toolchain
$ cd pirix-toolchain
$ ./prepare.sh
$ ./build.sh
{% endhighlight %}

To install the finished toolchain to `/opt/pirix-toolchain` execute
`./install.sh` as superuser. Be sure to add `/opt/pirix-toolchain/bin` to your
`$PATH`.

## Compiling

Now that all tools are in place you can start compiling the
system. Get a copy of the [source
code](/download/) and switch into the main directory.
The compilation is as simple as typing:

{% highlight bash %}
$ scons
{% endhighlight %}

## Testing

To test the system you just built, you can fire up qemu by running:

{% highlight bash %}
$ i386-system-qemu -kernel build/i386/pirix.img -nographic
{% endhighlight %}
