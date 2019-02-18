---
title: Getting Started
nav: true
toc: true
layout: page
---

This guide takes you through the process of installing the orbit runtime and compiler, compiling and running a first simple Orbit program. If orbit is already installed and working, you can find a more complete guide of the language and its standard library in the [documentation](/docuementation).

## Installing Orbit

### macOS Prerequisites

{% highlight bash %}
$ brew install clang cmake libcurl
{% endhighlight %}


### Linux Prerequisites

{% highlight bash %}
$ sudo apt-get install clang cmake libcurl-dev
{% endhighlight %}

### Building Orbit

Building and installing orbit is fairly simple. Orbit's build system is based on [CMake](https://cmake.org), but the simplest and preferred way to build the compiler, runtime and libraries is through the main build script.

{% highlight bash %}
$ git clone --recursive git@github.com:amyinorbit/orbitvm.git
$ cd orbitvm
$ ./build-script install
{% endhighlight %}

The build script provides more options, which you can get by calling `./build-script` with the `-h` (or `--help`) flag.

If you're building a version of orbit for development, and don't want to replace the stable version in your `$PATH`, you can pass the `-p` (or `--prefixed`) flag to the build script. The resulting binaries will be prefixed with a string indicating the build system and date like `orbit-darwin-i386-20170606-orbitc`.

Alternatively, you might want to build directly using CMake:

{% highlight bash %}
$ git clone --recursive git@github.com:amyinorbit/orbitvm.git
$ cd orbitvm
$ mkdir -p build && cd build
$ cmake ..
$ cmake --build . --target install
{% endhighlight %}

## Running Programs

To check that orbit is properly installed, create a file with the following Orbit source code:

{% highlight text %}
function main() {
    print("Hello from orbit!")
}
{% endhighlight %}

Orbit programs can be run in two ways. The first is similar to how java or C work: you compile your program to an Orbit Module File (`.omf`) that will be able to run on any Orbit VM. In a terminal window, invoke the `orbit` command with the `-c` flag on the file you created:

{% highlight bash %}
$ orbit -c helloworld.ob -o helloworld.omf
{% endhighlight %}

If you typed everything correctly, the compiler should create `helloworld.omf` next to `helloworld.ob`. You can then run the module file by invoking `orbit` with he `-r` (run) flag:

{% highlight bash %}
$ orbit -r helloworld.omf
Hello from orbit!
{% endhighlight %}

## Embedding Orbit
