---
layout: post
title:  "Exclude files from Jekyll"
date:   2016-03-30 13:50:59 -0500
tags: jekyll
---
I don't want `Gemfile` and `Gemfile.lock` and all sorts of other stuff in my `_sites` folder.  So, in my `_config.yml`:

{% highlight yaml %}
exclude: ['README.md', 'Gemfile.lock', 'Gemfile']
{% endhighlight %}
