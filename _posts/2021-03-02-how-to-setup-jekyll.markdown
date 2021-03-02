---
layout: post
title:  "How to setup a static website on Github Pages with Jekyll"
date:   2021-03-02 13:23:03 +1100
categories: jekyll update
---
Jekyll is a static site generator for making websites. Here are the steps I took to create a website with Jekyll on github pages on Mac Mojave 10.14.6. Thanks to Amanda Visconti's lesson [Building a static stie with Jekyll and Github Pages](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages) and the documentation at [Jekyll](https://jekyllrb.com/docs/installation/macos/)

Dynamic websites pull information from a database to populate each webpage, using content management systems like Drupal or Wordpress. Static websites do not use a CMS, instead each webpage is created statically using page templates that can be shared across all webpages in your site. Jekyll sites are typically quicker as there is no querying of a database to source information for the webpage. Jekyll creates static webpages which are hosted like any other website. Static pages also allow for easier version control as versions are simply text changes rather than databases changes.

## Installation

Jekyll dependencies:

- Ruby and Ruby Gems
- NodeJS

We also install the rbenv ruby environment manager

For website hosting, we use 

- Github Pages

To simplify version control management, instead of using command line, we use:

- Github Desktop

which provides a gui interface to commit, push, pull, merge changes to the main branch.


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


# Github Desktop

We install the Github Desktop app for easy version control


Visit the [GitHub Desktop site](https://desktop.github.com/) and click on the “Download GitHub Desktop” button to download the GitHub Desktop 
 
Configure by entering your github.com account credentials.





## My first jekyll website

Create your first jekyll website using the jekyll command to install a boilerplate site in your working directory

`cd ~/Documents/GitHub`

`jekyll new jekylldemo`

In `jekylldemo` folder, we find all the initial files needed to run the website..

`cd jekylldemo`

Next, we must set the baseurl, by

Open `_config.yml` file in a text editor. I use BBEdit. Change the baseurl line to be

`baseurl: "/jekylldemo"`

It is good practice, we need to also set the url. Change the url line to

`url: "localhost:4000"`



# Create repo from project folder

Open the GitHub desktop app. 

Create a repo from jekylldemo project folder 

Click `File` then `New Repository`

The repo name must match the folder name of your jekyll site, and the baseurl set in the _config.yml file, i.e. enter `jekylldemo` as the repo name

`Name`: `jekylldemo`

The Local Path should be set as below

`Local Path`: `~/Documents/GitHub`

This will create the GitHub folder in your Documents directory. This folder is where your repos managed with the GitHub Desktop app are cloned to by default.

For best practice, also tick the box to initialise with a README. Then click `Create Repository`

Then click `Publish` to publish site to GitHub Pages

Here you will also need to fix the yml file to point to the github.io webpage, by setting

`url: "jesscmoore.github.io"`

where the first part of the url is your github username.



# Configure GitHub Page source

Go to the online github repo

Click `Settings` and scroll down to `GitHub Pages` section of the page. Ensure that the GitHub Pages source is set to the main branch. This way pull merges into the main branch will be published to GitHub Pages.

You should see it show the url of your site as below where the first part of the url is your github username

[https://jesscmoore.github.io/jekylldemo/](https://jesscmoore.github.io/jekylldemo/)


# Personalise our site

Before we make changes to the site, we must create a new git branch. In the Branch tab of GitHUb Desktop, click the down arrow, then click `New Branch`, and set the branch name to "first-commit"

In text editor, open `_config.yml` file_, and change these settings



# Generate html

After updating page text, render to html with

`jekyll serve`



