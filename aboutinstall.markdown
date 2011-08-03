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

