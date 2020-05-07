# telegram file system

the internet is all messed up.

https://knightcolumbia.org/content/protocols-not-platforms-a-technological-approach-to-free-speech

@jack understands: https://twitter.com/jack/status/1204766078468911106

telegram's protocol provides the simplest data model and is handling a decent
amount of users right now.  these are the layers of protocol composition:

IP -> TCP -> HTTP -> MTProto -> literally any application

what everyone's missing is how powerful this is.  so to demonstrate, i'm going
to build a virtual filesystem + fuse bindings that rethinks the current
publication model of the internet.  think doing this to search for something
published by the nytimes:
```
$ tfs mount @nyt ~/news/nyt
$ rg ~/news/nyt -ie "free speech"
```

it also roughly means that all content accessible on the internet is now
available for use, which means we'll have to accept the boost license for
pretty much everything.  big changes.

## building

JNI Interface to [TDLib](https://github.com/tdlib/td)

See here:
https://github.com/tdlib/td/tree/master/example/java

## todo

* [ ] get example project from telegram building easily
* [ ] flesh out simple block and inode structure to store in channel messages
* [ ] determine what telegram api calls we'll actually need to care about to get basic functionality up and running
    * [ ] example code basically implements a simple chat application so honestly there's quite a bit of stuff to lean on
* [ ] primary focus at first will be the server implementation (which async links telegram and fuse)
    * [ ] then we can build a simple client that provides functionality like `tfs mount @gvacaliuc ~/foo/bar`
