---
title: "Adding-multimedia-content-to-your-posts"
comments: true
categories:
  - Jekyll
  - Tutorials
tags:
  - comments
  - layout
---


You want to make your blog pretty and make your post a little more descriptive.To do that you should be able to add multimedia content that reflect the topic that your blog and posts are about.

lets see how we can add images,videos and audio to our jekyll powered blog or website.


**Adding images**

the markdown code to add an image to your post :


`![image-title-here](/path/to/image.jpg){:class="img-responsive"})`

It is preferable to create an image or multimedia folder on the root of your project to better organise your file.

if the code above worked you should have your image working like this !

![Markdown-is-awesome](/assets/images/markdown.jpg){:class="img-responsive"})

**Adding videos**

To add add video your your Jekyll website you will first have include a plugin that will allow liquid, the templating system that Jekyll use to be be able to interpret the embeded code that you will will provide.

1.Under your _includes folder, add [this file](https://github.com/IziDevSpot/blog/blob/master/_includes/video) wich is an helper for displaying youtube and vimeo video.

{% highlight ruby %}

{% include video id="XsxDH4HcOWA" provider="youtube" %}

{% endhighlight %}

{% include video id="XsxDH4HcOWA" provider="youtube" %}



**Adding audio**

Soundclound is the most popular plaform for audio updloads and distribution over the internet. 
To add audio to your jekyll you first going create a new file under  `_plugins` direcatory and name it  `sc_player.rb` and copy/paste the following code :

