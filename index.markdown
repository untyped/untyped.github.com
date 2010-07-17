---
layout: default
title:  Untyped at Github
---

Welcome to the [Untyped][1] home page on [Github][2]. As you can see, we're only just getting started. Our code all lives <a href="http://github.com/untyped">here</a>. This page is currently just for installation instructions.

Please see the README, LICENCE and COPYING files in individual project repositories for terms of use.

How to build Untyped Racket libraries
-------------------------------------

We have a number of open source libraries for the [Racket][3] programming language. Most of our code is available through [PLaneT][4]. PLaneT is the preferred way of obtaining and running our code in most cases.

That said, there are some libraries that we haven't released to PLaneT, and there are some where the code here is a little newer than the latest PLaneT release. If you want to get hold of the latest and greatest version, or you want to hack on our code, this is how to do it:

1. We use a tool called [externals][5] to manage non-PLaneT dependencies between our libraries. Grab this tool first:

           sudo gem install ext

2. Clone the repository you want to use:

           git clone git://github.com/untyped/unlib.git

3. Use `ext` to download any dependencies that aren't on PLaneT:

           cd unlib ; ext update

   This will create a directory called `planetdev` and a subdirectory for each dependency.

4. Use `build.ss` to compile the code:

           ./build.ss compile
    
   This will create a local PLaneT cache in a directory called `planet` containing PLaneT dependencies, and install development links for the libraries in `planetdev`. The first run of `build.ss` can take a few minutes to complete.

You may want to set up your shell with the right `PLTVERSION` and `PLTPLANETDIR` so you can use `racket` and `raco` directly. You can do this by running:

        source `./build.ss envvars`

[1]: http://untyped.com
[2]: http://github.com
[3]: http://www.racket-lang.org
[4]: http://planet.racket-lang.org
[5]: http://nopugs.com/ext-tutorial
