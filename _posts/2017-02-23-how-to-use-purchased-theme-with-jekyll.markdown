---
title: "How to use purchased theme with jekyll"
comments: true
categories:
  -Jekyll
  -Tutorials
tags:
  - comments
  - layout
---

In this Tutorial you are going to learn how to  use a purchased theme for your website or blog powered by jekyll.

A theme for Jekyll cost more or less $ 24 dollar on [ThemeForest](https://themeforest.net/?ref=izidevspot/category/static-site-generators/jekyll). All you have to do is download the zip package of your purchased theme in the folder directory where your project will live.

One extracted you will open a terminal window into the directory of your extracted content where the `_config.yml` is located.

One you are there, you can run the command  `jekyll serve` . Go to your browser window and type the default address/port for your jekyll site : `http://127.0.0.1:4000/`

If everything went fine you will typically see the default content of your purchased theme. That’s mean that your theme is working and you can just make the changes and add your customized content. Follow these previous [tutorial]({% post_url 2017-02-22-getting-started-with-jekyll %}) if you are not sure of how to do so.

*Some problems you might encounter :*

**Missing dependencies:** 
If you get this error when trying to serve your new theme you can gent the dependency name on the console and run the command :
Gem install dependency-name

**Page not found:**
The baseurl is responsible of receiving the address of the subpath to launch your website .
On your `_config.yml` your baseurl should stay empty: 

`baseurl: ""`


Hopefully this little tutorial hepled you setting up a [purchased theme](https://themeforest.net/?ref=izidevspot/category/static-site-generators/jekyll) for your website or blog. Namaste !
