# Hello World

This repository contains a simple C application, and demonstrates how to
build and package it so it can be installed on another computer.

## Building

```
clang -g main.c -o hello
```

You'll need to prep a directory:

```
mkdir -p install/opt/local/hello/bin/
cp hello install/opt/local/hello/bin/
```

Once built, you can create a flat package

```
pkgbuild --root install --identifier org.phaka.hello hello.pkg
```

To install it, you can then run

```
sudo installer -pkg hello.pkg -target /
```

## References

* https://matthew-brett.github.io/docosx/flat_packages.html
* http://bomutils.dyndns.org/tutorial.html