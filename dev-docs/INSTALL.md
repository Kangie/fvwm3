Installation Instructions
=========================

FVWM3 uses automake and autotools as its build process.

Dependencies
============

Docker
======

The `fvwm3` repository has a Dockerfile which can be used to build the
repository.  This is the same Docker image as used by Github Actions.

Manually
========

FVWM3 has the following dependencies.  Note that across different
distributions, the development package names will differ.  The names listed
below are examples to help you find the appropriately named package for the
system in use.

## Core dependencies

* libevent-dev (>= 2.0)
* libfontconfig-dev
* libfreetype6-dev
* libx11-dev
* libxext-dev
* libxft-dev
* libxrandr-dev (>= 1.5)
* libxrender-dev
* libxt-dev

## Optional dependencies

* asciidoctor
* libfribidi-dev
* libncurses5-dev
* libpng-dev
* libreadline-dev
* librsvg-dev
* libsm-dev
* libxcursor-dev
* libxi-dev
* libxpm-dev
* sharutils

Generating documentation
========================

To generate `fvwm3`'s documentation:

1. Install `asciidoctor`
2. To generate manpages:  pass `--enable-mandoc` to `./configure`
3. To generate HTML docs: pass `--enable-htmldoc` to `./configure`

`fvwm3` won't compile documentation by default, so it's opt-in.

Installing From Git
===================

## Autotools

FVWM3 has a bootstrap script to generate `configure` and associated files.
Run the following command chain to generate the `configure` script and build
the project:

```console
user@host:~/fvwm3$ ./autogen.sh
user@host:~/fvwm3$ ./configure
user@host:~/fvwm3$ make
user@host:~/fvwm3$ sudo make install
```

## Meson

FVWM3 supports the Meson build system. To build with Meson first configure the build then use the 'Ninja' tool to compile and install:

```console
user@host:~/fvwm3$ meson setup build
user@host:~/fvwm3/builddir$ ninja -C build
user@host:~/fvwm3/builddir$ ninja -C build install
```

Ninja also has an `uninstall` target:

```console
user@host:~/fvwm3/builddir$ ninja -C build uninstall
```

To configure the build, pass options to `meson setup` (or `meson configure «builddir»` if the project has already been setup):

```console
user@host:~/fvwm3$ meson setup build --prefix=/usr --buildtype=release -Dmandoc=true
```

For a full list of flags and possible values, see `meson configure meson.build` or point `meson configure` at an existing builddir with no arguments.

Installing From Release Tarball
===============================

Release tarballs will come bundled with `./configure` already, hence:

```console
user@host:~/fvwm3-1.2.3$ ./configure
user@host:~/fvwm3-1.2.3$ make
user@host:~/fvwm3-1.2.3$ sudo make install
```

or

```console
user@host:~/fvwm3$ meson setup build
user@host:~/fvwm3/builddir$ ninja -C build
user@host:~/fvwm3/builddir$ meson install -C build
```

As with most things, if the default options aren't appropriate for your needs,
see `./configure --help` or `meson configure meson.build` for appropriate options.
