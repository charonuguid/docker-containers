![Hugo](https://raw.githubusercontent.com/gohugoio/hugoDocs/master/static/img/hugo-logo.png)

A Fast and Flexible Static Site Generator built with love by [bep](https://github.com/bep), [spf13](http://spf13.com/) and [friends](https://github.com/gohugoio/hugo/graphs/contributors) in [Go][].

[Website](https://gohugo.io) |
[Forum](https://discourse.gohugo.io) |
[Developer Chat (no support)](https://gitter.im/gohugoio/hugo) |
[Documentation](https://gohugo.io/overview/introduction/) |
[Installation Guide](https://gohugo.io/overview/installing/) |
[Contribution Guide](CONTRIBUTING.md) |
[Twitter](http://twitter.com/gohugoio)

[![GoDoc](https://godoc.org/github.com/gohugoio/hugo?status.svg)](https://godoc.org/github.com/gohugoio/hugo)
[![Linux and macOS Build Status](https://api.travis-ci.org/gohugoio/hugo.svg?branch=master&label=Linux+and+macOS+build "Linux and macOS Build Status")](https://travis-ci.org/gohugoio/hugo)
[![Windows Build Status](https://ci.appveyor.com/api/projects/status/a5mr220vsd091kua?svg=true&label=Windows+build "Windows Build Status")](https://ci.appveyor.com/project/bep/hugo/branch/master)
[![Dev chat at https://gitter.im/gohugoio/hugo](https://img.shields.io/badge/gitter-developer_chat-46bc99.svg)](https://gitter.im/spf13/hugo?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Go Report Card](https://goreportcard.com/badge/github.com/gohugoio/hugo)](https://goreportcard.com/report/github.com/gohugoio/hugo)

## Overview

Hugo is a static HTML and CSS website generator written in [Go][].
It is optimized for speed, ease of use, and configurability.
Hugo takes a directory with content and templates and renders them into a full HTML website.

Hugo relies on Markdown files with front matter for metadata, and you can run Hugo from any directory.
This works well for shared hosts and other systems where you don’t have a privileged account.

Hugo renders a typical website of moderate size in a fraction of a second.
A good rule of thumb is that each piece of content renders in around 1 millisecond.

Hugo is designed to work well for any kind of website including blogs, tumbles, and docs.

#### Supported Architectures

Currently, we provide pre-built Hugo binaries for Windows, Linux, FreeBSD, NetBSD, macOS (Darwin), and [Android](https://gist.github.com/bep/a0d8a26cf6b4f8bc992729b8e50b480b) for x64, i386 and ARM architectures.

Hugo may also be compiled from source wherever the Go compiler tool chain can run, e.g. for other operating systems including DragonFly BSD, OpenBSD, Plan 9, and Solaris.

**Complete documentation is available at [Hugo Documentation][].**

## About This Container

This was created to be used to run on Visual Studio Code as part of the IDE's Remote Containers development feature. But it should not stop you from using this for anything else.

This container uses the `extended` version of Hugo v0.65.3

## Using This Container

To generate a new site:

```
docker run -it --rm -v $PWD:/source headgeekette/hugo-docker new site ${NAME_OF_SITE}
```

To generate a new post:

```
docker run --rm -v $PWD:/source headgeekette/hugo-docker new ${NAME_OF_POST}
```

You might have to change ownership and group in order to edit the necessary files after creating a new site and/or new post.

When running as a server, do not forget to specify the base url and bind to 0.0.0.0.

```
docker run --rm -p 1313:1313 -v `pwd`:/source headgeekette/hugo-docker \
     server \
    -b http://localhost:1313 --bind=0.0.0.0
```
