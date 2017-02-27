---
title: "2017-02-23-adding-multimedia-content-to-your-posts"
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


`![image-title-here](/path/to/image.jpg){:class="img-responsive"}`

It is preferable to create an image or multimedia folder on the root of your project to better organise your file.

if the code above worked you should have your image working like this !

![Markdown-is-awesome](/multimedia/markdown.jpg){:class="img-responsive"}

**Adding videos**

A solution to easyly embed video from youtube is provided on github by [@joelverhagen](https://gist.github.com/joelverhagen/1805814)

The process is really simple, on your root folder create a new folder if not exist called _plugin, create a new file inside this directory called youtube.rb :

{% highlight ruby %}
class YouTube < Liquid::Tag
  Syntax = /^\s*([^\s]+)(\s+(\d+)\s+(\d+)\s*)?/

  def initialize(tagName, markup, tokens)
    super

    if markup =~ Syntax then
      @id = $1

      if $2.nil? then
          @width = 560
          @height = 420
      else
          @width = $2.to_i
          @height = $3.to_i
      end
    else
      raise "No YouTube ID provided in the \"youtube\" tag"
    end
  end

  def render(context)
    # "<iframe width=\"#{@width}\" height=\"#{@height}\" src=\"http://www.youtube.com/embed/#{@id}\" frameborder=\"0\"allowfullscreen></iframe>"
    "<iframe width=\"#{@width}\" height=\"#{@height}\" src=\"http://www.youtube.com/embed/#{@id}?color=white&theme=light\"></iframe>"
  end

  Liquid::Template.register_tag "youtube", self
end
{% endhighlight %}

Then you can use the following code with the youtube video url you want to display (dont't forget to replace with your video id):

{% raw %}
`{% youtube oHg5SJYRHA0 %}`

{% endraw %}

Now you can see the result:

{% youtube oHg5SJYRHA0 %}




**Adding audio**

Soundclound is the most popular plaform for audio updloads and distribution over the internet. 
To add audio to your jekyll you first going create a new file under  `_plugins` direcatory and name it  `sc_player.rb` and copy/paste the following code :

{% highlight ruby %}
# SoundCloud player tag.
#
# Generates a SoundCloud player widget from any valid URI: track, playlist or user.
#
# Usage:
#
#   {% sc_player uri %}
#
# Example:
#
#   {% sc_player https://soundcloud.com/waek/daze-ft-girl-is-tough-new-york %}
#
# Configuration (in _config.yml):
#
#   sc_player:
#     auto_play: false
#     buying: true
#     liking: true
#     download: true
#     sharing: true
#     show_artwork: true
#     show_comments: true
#     show_playcount: true
#     show_user: true
#     start_track: 0
#
# Author: Mathieu Bernard
# Plugin Source: http://github.com/itsbrnrd/jekyll_sc_player
# Site Source: http://github.com/itsbrnrd/jekyll_sc_player
# Plugin License: MIT

require 'uri'

module Jekyll
  class SCPlayerTag < Liquid::Tag
    def initialize(tag_name, config, token)
      super

      @uris  = URI.extract(config)

      @config = Jekyll.configuration({})['sc_player'] || {}
    end

    def render(context)
      html = ""

      @uris.each_with_index do |uri, index|
        html << "<iframe id='sc-widget-#{index}' src='https://w.soundcloud.com/player/?url=#{uri}&#{URI.encode_www_form(@config)}' width='100%' scrolling='no' frameborder='no'></iframe>"
      end
      return html
    end
  end
end

Liquid::Template.register_tag('sc_player', Jekyll::SCPlayerTag)
{% endhighlight %}

then add this snipet to your `_config.yml` :

{% highlight ruby %}
sc_player:
  auto_play: false # Whether to start playing the widget after it’s loaded
  buying: true # Show/hide buy buttons
  liking: true # Show/hide like buttons
  download: true # Show/hide download buttons
  sharing: true # Show/hide share buttons/dialogues
  show_artwork: true # Show/hide artwork
  show_comments: true # Show/hide comments
  show_playcount: true # Show/hide number of sound plays
  show_user: true # Show/hide the uploader name
  start_track: 0 # Preselects a track in the playlist, given a number between 0 and the length of the playlist.

  {% endhighlight %}


  Now you can use this code to embed the song or playlist you want from soundcloud :

{% raw %}
  `{% sc_player https://soundcloud.com/dj-k-slim/tanbou-rmx-by-dj-k-slim %}`

  {% endraw %}

Lets enjoy the result !

  {% sc_player https://soundcloud.com/dj-k-slim/tanbou-rmx-by-dj-k-slim %}
