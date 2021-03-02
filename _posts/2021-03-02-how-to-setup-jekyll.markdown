---
layout: post
title:  "How to setup a static website on Github Pages with Jekyll"
date:   2021-03-02 13:23:03 +1100
categories: jekyll update
---
Jekyll is a static site generator for making websites. Here are the steps I took to create a website with Jekyll on github pages on Mac Mojave 10.14.6. Thanks to Amanda Visconti's lesson [Building a static stie with Jekyll and Github Pages](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages)

Dynamic websites pull information from a database to populate each webpage, using content management systems like Drupal or Wordpress. Static websites do not use a CMS, instead each webpage is created statically using page templates that can be shared across all webpages in your site. Jekyll sites are typically quicker as there is no querying of a database to source information for the webpage. Jekyll creates static webpages which are hosted like any other website. Static pages also allow for easier version control as versions are simply text changes rather than databases changes.

## Installation

Jekyll dependencies:

- Ruby and Ruby Gems
- NodeJS

We also install the rbenv ruby environment manager

For website hosting, we use 

- Github Pages


# Ruby and Ruby Gems

We install both Ruby and Ruby Gems. Gems is the package manager for Ruby.

`brew install ruby`

Ruby is on Mac by default, however to use the brew version we add this new ruby binary to our `$PATH` and source the new path.

`echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.bash_profile`

`source ~/.bash_profile`

Check it is pointing to our new ruby setup

`which ruby`

`ruby -v`

This is the current stable version of Ruby.

The Ruby build installs a non-Homebrew OpenSSL for each Ruby version installed and these are never upgraded. To link Rubies to Homebrew's OpenSSL 1.1 (which is upgraded) we set the ruby openssl option

`echo 'export RUBY_CONFIGURE_OPTS="--with-openssl-dir=$(brew --prefix openssl@1.1)"' >> ~/.bash_profile`

Now update ruby gems with

`gem install rubygems-update`

This gives an install warning that `~/.gem/ruby/3.0.0/bin` is needed in our PATH, to allow gem executables to run.

`echo 'export PATH="/Users/u9904893/.gem/ruby/3.0.0/bin:$PATH"' >> ~/.bash_profile`


Check that jekyll points to our home directory with

`gem env`



# rbenv 

We also install `rbenv` to manage environments with different ruby versions.

`brew install rbenv`

And set up rbenv integration with our shell

`rbenv init`

We can check our rbenv installation with

`curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash`

Setup rbenv to load rbenv automatically 

`echo 'eval "$(rbenv init -)"' >> ~/.bash_profile`


# NodeJS

`brew install node`


# Jekyll

Install the bundler and jekyll gems

`gem install jekyll bundler`

If this doesn't work, do `gem install --user-install bundler jekyll`


# Github Pages

We install the Github Desktop app for easy version control


Visit the [GitHub Desktop site](https://desktop.github.com/) and click on the “Download GitHub Desktop” button to download the GitHub Desktop 
 
Configure by entering your github.com account credentials.

Open the GitHub desktop app. Creating a local test repo should add a Github directory to your home directory. If it doesn't, do

`mkdir ~/Documents/GitHub`




## My first jekyll website

Create your first jekyll website using the jekyll command to install a boilerplate site in your working directory

`cd ~/Documents/GitHub`

`jekyll new jekylldemo`

In `jekylldemo` folder, we find all the initial files needed to run the website..

`cd jekylldemo`



# Generate html

After updating page text, render to html with

`jekyll serve`



