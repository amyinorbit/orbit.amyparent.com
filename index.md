---
layout: home
title: The Orbit Programming Language
---

Orbit is a small, fast language at the boundary between procedural and functional programming, easy to embed in a C application. Orbit is strongly typed, provides intuitive type inference, and is easy to pick up.

{% highlight txt %}

function sayHello(name: String) => Void {
    print("Hello, " + name + "! Welcome to Orbit!")
}

function main() {
    var name: String = Console.parameters[1]
    sayHello(name)
}
{% endhighlight %}

Orbit is currently under development. The Orbit Runtime is working (but could still do with some work), and the compiler is in the early development stages (the parser is done, semantic analyser underway). Interested? You can contribute to [Orbit's source code](/source-code/), or [get started with the current version](/getting-started/).

-- [Amy Parent](http://amyparent.com)