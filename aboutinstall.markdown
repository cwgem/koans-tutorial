Getting Ruby
============

Implementations
---------------

Before beginning the journey into Ruby, one needs to get a hold of it. This guide will be working off the [latest stable version of Ruby](http://www.ruby-lang.org/en/downloads/), which is 1.9.2 as of writing. Now, there are many implementations available. The official one is known as MRI (Matz's Ruby Interpreter), named after the creator of the Ruby language, Yukihiro "Matz" Matsumoto. This implementation is sometimes referred to as CRuby. If you're starting out with Ruby, it's recommended to work with the MRI version. Most of the tutorials should work fine on any implementation (in fact I have all of the ones listed below, and will try to test code in all of them as much as possible), but there is still a chance you might stumble across an issue that requires a bit more advanced troubleshooting. I'll leave the decision up to the reader as to how comfortable they are with experimenting with different ruby implementations.

Below is a short list (albeit not comprehensive) of some alternatives to the MRI implementation:

 * [JRuby](http://www.jruby.org/) - Built it pure Java, it enables Ruby to be run on the JVM (Java Virtual Machine). This provides access to the VM optimizations. For those really in the experimental mode, the master branch has implemented many interesting features of OpenJDK 7 specifically targeting dynamic languages.
 * [Rubinius](http://rubini.us/) - While a good portion of the core library code for MRI is written in C, Rubinius looks to take a different approach and use Ruby as much as possible. The VM it uses is written in C++ instead of just C. Other parts are written exclusively in Ruby if possible.
 * [Ruby Enterprise Edition](http://www.rubyenterpriseedition.com/) - Based off of the 1.8 Ruby series, it targets Ruby used in enterprise environments. Features include the ability to configure the garbage collector and decreased memory usage. 
 * [Macruby](http://www.macruby.org/) - A Mac specific implementation of Ruby. It utilizes MacOS X core technologies and provide the ability to work with many of the MacOS X Frameworks. 
 * [IronRuby](http://ironruby.net/) - For Windows users, IronRuby provides integration with the .NET framework and Visual Studio integration. Microsoft is involved in this project, ensuring that it is as compatible as possible.
 * [MagLev](http://ruby.gemstone.com/) - Targeting users looking into scalability, MagLev runs a server which allows for caching and object persistence. Make sure you know what you're doing if you decide to use this for the tutorial!
 * [Cardinal](https://github.com/parrot/cardinal) - Ruby compiler for the Parrot Virtual Machine (the virtual machine for Perl 6). Much like .NET and JVM, Parrot supports multiple language backends, thought it sets itself out by specifically targeting dynamic languages. Know what you're doing if you plan to use this for the tutorial!

Installing With rvm (excluding Windows)
---------------------------------------

When working with this tutorial, chances are a majority of users will be using a single version of a single Ruby implementation. However, the issue arrises when later on the user may wish to try out other Ruby implementations or versions. This can require complex path mangling that can cause much tearing out of hair. Instead, rvm provides an easy way to install multiple versions of multiple Ruby implementations on the same machine. Not only that, but it does the installation local to the user so increased privileges are not required for installation of many external Ruby libraries (known as gems, which will be discussed later on). As such it is the preferred way to install Ruby for a good portion of the Ruby community.

Installation of rvm is rather straightforward. It's a simple scrip that is downloaded and ran from the command line. Once the installation is finished a small adjustment of the shell profile is required. The full details can be found on the [rvm install page](http://beginrescueend.com/rvm/install/). MRI 1.9.2, which is the latest stable version at writing, can be installed and utilized as follows:

```
rvm install 1.9.2
...
rvm use 1.9.2
```

Installing with pik (Windows)
-----------------------------

Since rvm is [not supported for Windows users](http://beginrescueend.com/support/faq/), an alternative known as [pik](https://github.com/vertiginous/pik/) was created with these users in mind. As of writing it currently supports MRI, JRuby, and IronRuby implementations. It's recommended to use the [installer](https://github.com/vertiginous/pik/downloads) in order to get pik setup for the first time. Once this is done, you can use pik to install the Ruby implementation of liking:

```
Usage: pik install|in [options]

Downloads and installs different ruby versions.

  Choices are: ruby, jruby, or ironruby

  If no version is specified, the latest version will be installed.
  Download and install locations can be configured with 'pik config'.

  Examples:

    # install the latest version of JRuby (currently 1.4.0RC1)
    >pik install jruby

    # install the latest 1.8 version of MinGW Ruby 
    >pik install ruby 1.8    

    -V, --version                    Pik version

```

In the case of this tutorial, it is recommended to use the latest stable version of the MRI, which can be done as follows:

`pik install ruby`

From there you can use Ruby by entering the following command in the shell:

`pik use ruby`

Windows and Mac OSX Installer
-----------------------------

For those that wish for an installer based solution, installers are available for MacOSX and Windows. Do note that Mac OSX comes with Ruby and Ruby On Rails already installed. Below are the installer websites:

 * [Windows Installer](http://rubyinstaller.org/)
 * [Mac OSX Installer](http://rubyosx.rubyforge.org/)

Linux / BSD Packages
--------------------

Below ways to install Ruby using package managers of a few Linux and BSD Operating Systems. Note that some of installations also describe the Ruby on Rails installation process as well.

 * [Debian](http://www.debian-administration.org/articles/329)
 * [Ubuntu](https://help.ubuntu.com/community/RubyOnRails)
 * [Fedora 10 and 11](http://www.technetra.com/2009/04/22/howto-setting-up-ruby-on-rails-for-fedora-10-and-11/)
 * [RedHat](http://www.alethe.com/brad/2008/04/ruby-on-rails-for-rhel-5/)
 * [OpenBSD](http://myutil.com/2007/11/5/building-ruby-on-openbsd-from-source)
 * [NetBSD](http://www.ezunix.org/index.php/Install_Gitorious_with_Ruby_1.9_on_NetBSD#Install_Ruby)
 * [FreeBSD](http://jasonnoble.org/2008/09/installing-ruby-on-rails-in-freebsd.html)

Source Code Installation
------------------------

The latest version of the ruby source code can be downloaded from the [official Ruby website](http://www.ruby-lang.org/en/downloads/). From there the compilation process is fairly standard:

```
./configure # add --prefix=/my/install/path if needed
make # compiling as a non-privileged user is always a good idea
sudo make install # or su to root
```

Should any issues come up, check the [Ruby bug tracker](http://redmine.ruby-lang.org/) to see if it is a known issue.

Code Editors
------------

While working with this tutorial, it will become necessary at some point to start writing scripts. While any text editor will do, there are quite a lot of editors available that support Ruby. Some are very unobtrusive and offer simple syntax highlighting, while others provide a complete solution with autocomplete and debugging capabilities. Finally, some are cross platform, while others are tied to a specific operating system (TextMate for example only runs on Mac). 

The list of editors is fairly large, and I've created a rather comprehensive list of them at [the Wiki that this tutorial is hosted on](https://github.com/cwgem/koans-tutorial/wiki/Ruby-Code-Editors). My hope is that the list will provide with a starting point in selecting the IDE that is  the most comfortable to work with.