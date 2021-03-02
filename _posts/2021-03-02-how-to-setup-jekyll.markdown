--- layout: post 
title:  "How to setup Jekyll!" 
date:   2021-03-02 10:23:03 +1100 
categories: jekyll update 
--- 

Jekyll is a static site generator for making websites. Here are the steps I took to create a website with Jekyll on github pages on Mac Mojave 10.14.6. Thanks to Amanda Visconti's less on [Building a static stie with Jekyll and Github Pages][https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages]

Dynamic websites pull information from a database to populate each webpage, using content management systems like Drupal or Wordpress. Static websites do not use a CMS, instead each webpage is created statically using page templates that can be shared across all webpages in your site. Jekyll sites are typically quicker as there is no querying of a database to source information for the webpage. Jekyll creates static webpages which are hosted like any other website. Static pages also allow for easier version control as versions are simply text changes rather than databases changes.

# Setup

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %} def print_hi(name) 
	puts "Hi, #{name}" 
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home 
[jekyll-gh]: https://github.com/jekyll/jekyll 
[jekyll-talk]: https://talk.jekyllrb.com/
