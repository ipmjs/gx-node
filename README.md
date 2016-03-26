
# gx-node [PRE-ALPHA]

> A [gx package manager](https://github.com/whyrusleeping/gx) environment tool **for node**.

[![](https://img.shields.io/badge/freenode-%23gx-blue.svg?style=flat-square)](http://webchat.freenode.net/?channels=%23ipfs,%23gx)

Please note that **this project is under development**, some features proposed may not be
implemented and any information provided is subject to change. Currently, there is not even any source code for this specific gx environment tool, **we must plan!**.

## Table of Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
  - [Creating a package](#creating-a-package)
  - [Importing a package](#importing-a-package)
- [Getting involved](#getting-involved)
- [License](#license)

## Requirements

Users should have [IPFS](https://ipfs.io) of at least version `0.4.0`. gx can use a
public gateway to download node packages as gx dependencies, but if you wish to publish a
package to the network, a locally running [IPFS daemon](https://github.com/ipfs/go-ipfs)
is an absolute requirement.

## Installation

```
go get -u github.com/ipmjs/gx-node
```

This will download the `gx-node` source into `$GOPATH/src/github.com/ipmjs/gx` and build and install a binary to `$GOPATH/bin`. To modify `gx-node`, just change the source in `$GOPATH/src/github.com/ipmjs/gx` and run `go build`.

## Usage

```
NAME:
   gx-node - A gx environment tool for node.

USAGE:
   gx-node [global options] command [command options] [arguments...]

VERSION:
   0.0.0

AUTHOR(S):
   whyrusleeping
   reimertz
   lukeeeebennett

COMMANDS:
   update	Update a node package that is already a gx dependency.
   import	Import a node package as a gx dependency.
   hook		Node-specific hooks called by gx.
   help, h	Shows a list of commands or help for one command.

GLOBAL OPTIONS:
   --help, -h		Shows a list of commands or help for one command.
   --version, -v	Shows version information.
```

### Creating a package

In the root directory of your node package, just run:

```
gx init --lang=node
```

gx will create a new `package.json` for you with some default values.
From there, all you *have* to do is run `gx publish` and gx will return a hash address
for your new package.

*You will need a running IPFS daemon for this to work.*

### Importing a package

Importing an existing node package from gx is easy, just grab its hash address from
somewhere, and run:

```
gx import <package-hash>
```

## Getting involved

If you would like to get involved with `gx-node` or `gx`, please open an
[issue](https://github.com/ipmjs/gx-node/issues) or stop by #gx and #ipfs on freenode irc!

## License

```
The MIT License (MIT).

Copyright (c) 2016 Luke Bennett.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```