---
title: "Adding multimedia content to your posts"
comments: true
categories:
  - Jekyll
  - Tutorials
tags:
  - comments
  - layout
---

Besides text, you should be able to add multimedia content to your post.

let us see how we can add images, videos, and audio to our Jekyll powered blog or website.


**Adding images**

the markdown code to add an image to your post :


`<img src="{{ site.baseurl }}/path/to/img/toto.jpg">`

It is preferable to create an image or multimedia folder on the root of your project to better organize your file.

if the code above worked you should have your image working like this !
<img src="{{ site.baseurl }}/assets/images/markdown.jpg">


**Adding videos**

To add video your-your Jekyll website you will first have to include a plugin that will allow liquid, the templating system that Jekyll use to be-be able to interpret the embedded code that you will-will provide.

1.Under your _includes folder, add [this file](https://github.com/IziDevSpot/blog/blob/master/_includes/video) which is an helper for displaying youtube and vimeo video.
{% highlight ruby %}
{% raw %}
{% include video id="XsxDH4HcOWA" provider="youtube" %}
{% endraw %}
{% endhighlight %}
{% include video id="XsxDH4HcOWA" provider="youtube" %}



**Adding audio**

SoundCloud is the most popular platform for audio uploads and distribution over the internet. 
To add audio to your Jekyll you first going create a new file under  `_plugins` directory and name it  `sc_player.rb` and copy/paste the following code:
