# sef.kloninger.com AKA sefk.github.io 

This is my personal blog. It is a Nikola static site hosted by
Github pages.  This repo contains the source files. The repo for
the target files, [sefk.github.io](http://github.com/sefk/sefk.github.io)
is included as a submodule.

# Instructions

The general workflow is:

1. **Write**. I like writing in Markdown with vi. Green characters on a
   black background. 

2. **Review**. Nikola has a nice feature to automatically rebuild your
   project whenever something changes.  The -b option fires up a
   localhost browser that refreshes with every save.  Very nice
   workflow.  Command is ```nikola auto -b -p 8888```. The port
   is in case the default port (8000) collides your dev environment.

3. **Publish**.  Check in the changes to this repo and the ```output``` 
   subdirectory which has the build products.

4. **Repeat**


## Install Notes

The target repo for the content is a git submodule. After you first checkout, do a
```git submodule init``` to pick it up.

### lxml error

If you're seeing this:

    fatal error: 'libxml/xmlversion.h' file not found
    error: command 'cc' failed with exit status 1

Then try this:

    brew install libxml2
    brew install libxslt
    brew link libxml2 --force
    brew link libxslt --force

    CPATH=/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.9.sdk/usr/include/libxml2 CFLAGS=-Qunused-arguments CPPFLAGS=-Qunused-arguments pip install lxml

Not sure the brew steps are req'd or not. That last step is what did it. From [this StackOverflow answer](http://stackoverflow.com/questions/19548011/cannot-install-lxml-on-mac-os-x-10-9) 
