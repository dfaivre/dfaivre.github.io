---
layout: post
title:  "Disqus Comments in Jekyll"
date:   2016-03-30
tags: jekyll disqus
---

God this took a long time.  I finally just used the [Jekyll Now](https://github.com/barryclark/jekyll-now/blob/master/_includes/disqus.html)
starter project and it magically worked:

**Add disqus.html to _includes**

{% highlight html %}
{% raw %}
<div id="disqus_thread"></div>
<script type="text/javascript">
    var disqus_shortname = '{{ site.disqus }}';
	    (function() {
	        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
	        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
	        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
	    })();
</script>
<noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endraw %}
{% endhighlight %} 

**Add disqus to _config.yml**

{% highlight yaml %}
disqus: disqus-shortname
{% endhighlight %}

**Include the disqus html in your _layouts/posts.html**

You can add a variable to your front matter to toggle if the comments show too.
Here, I want them on by default, so I use a falsy `hide_comments`.

{% highlight html%}{% raw %}
{% unless page.hide_comments %}
    {% include disqus.html %}
{% endunless %}{% endraw %}
 {% endhighlight html%}