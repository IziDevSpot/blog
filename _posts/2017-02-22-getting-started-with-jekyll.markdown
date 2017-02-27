---
title: "Getting started with Jekyll"
comments: true
categories:
  -Jekyll
  -Tutorials
tags:
  - comments
  - layout
---


Jekyll is a really innovative solution for building static websites and blogs. It have some really great features and advantages taking you away of the struggle of maintenance as its structure and is simple and powerful.

The  objective of this tutorial is to get you started with the knowledge you need to build your website or blog with jekyll.

First thing first, lets install Jekyll :

Before installing Jekyll you have to make sure that you have a ruby on rails environment setup allready, more information about installing ruby on rails can be found here: http://installrails.com/steps/choose_os

If you already have ruby on rails installed, you can type this command on your terminal or windows command prompt:


{% highlight ruby %} $ gem install jekyll bundler {% endhighlight %}

Now that Jekyll is installed, you can go ahead and create a new project that will be a directory with all the necessary files of your fancy website or awesome blog :

Run those 2 commands to create your project and move to the new directory created:

{% highlight ruby %}jekyll new your-fancy-website

cd your-fancy-website

{% endhighlight %}
 
Now you can run this command to run your new created project on your local server and see its structure :

 {% highlight ruby %}

 bundle exec jekyll serve
{% endhighlight %}

At this time your project running on  'http://127.0.0.1:4000/' should looks like this :




Now it's time to understand the file structure in your project folder and see how you can add pages,new posts configure your overall website and blog.

This how your your project directory should looks now :

The `config.yml` is where your general configuration for your website goes. 

You can go ahead and replace the content like `name`, `description`, `twitter_username` with yours :

 {% highlight ruby %}

title: Izidevspot's blog
email: izidevspot@gmail.com
description: > # this means to ignore newlines until "baseurl:"
  Write an awesome description for your new site here. You can edit this
  line in _config.yml. It will appear in your document head meta (for
  Google search results) and in your feed.xml site description.
baseurl: "" # the subpath of your site, e.g. /blog
url: "" # the base hostname & protocol for your site, e.g. http://example.com
twitter_username:
github_username:  izidevspot

{% endhighlight %}

To learn more about the file structure that jekyll uses you  can read the [docs][docs].

**Now lets write a blog post and see how it works**.

On your folder directory go under `_posts` and create a new file, the name of the file should follow this example : `YEAR-MONTH-DAY-title.markdown`

 [Markdown][Markdown] is a text to html conversion tool used to convert plain text to html. 

 your new post will be constisted of 2 parts:

**A [YAML font matter][YAML-font-matter] block begining the document that define the settings for your blog post like this:**

 {% highlight ruby %}
---
layout: post
title:  "Getting started with Jekyll"
date:   2017-02-22 11:22:39 -0500
categories: Tutorials
---
{% endhighlight %}

**The body of the document that can be writed in html or markdown**.

Now lets see how you can create pages.


You can create pages by either using `markdown` or `html` under the root folder of your project.

more references can be found on the [jekyll documentation page](https://jekyllrb.com/docs/pages/)

*Next steps:*

[how to  use purchased theme with jekyll](#)

[How to add comments to your blog post](#)

[How to add images to your blog post](#)

[Deploy your blog to github page ](#)

[docs]: https://jekyllrb.com/docs/structure/
[Markdown]: https://daringfireball.net/projects/markdown/

[YAML-font-matter]: https://jekyllrb.com/docs/frontmatter/