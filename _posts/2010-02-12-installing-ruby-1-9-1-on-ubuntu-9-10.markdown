---
layout: post
title: Installing Ruby 1.9.1 On Ubuntu 9.10
---

A quick guide for getting Ruby 1.9.1 installed from source on Ubuntu 9.10 (Karmic).

Before installing Ruby, ensure you have the following packages:

    apt-get install build-essential libssl-dev libreadline5 libreadline5-dev zlib1g zlib1g-dev

Download source, extract, configure, make, test and install:

    mkdir ~/src && cd ~/src
    wget ftp://ftp.ruby-lang.org/pub/ruby/1.9/ruby-1.9.1-p376.tar.gz
    tar -xvf ruby-1.9.1-p376.tar.gz
    cd ruby-1.9.1-p376
    ./configure
    make
    make test
    make install

You'll now have Ruby installed:

    ruby -v
    > ruby 1.9.1p376 (2009-12-07 revision 26041) [i686-linux]
    gem -v
    > 1.3.1

The latest version of RubyGems is 1.3.5, so quickly upgrade:

    gem update --system
