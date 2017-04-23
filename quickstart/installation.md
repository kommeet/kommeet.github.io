---
layout: docs
subTitle: Installation
quickstart: true
---
# Installation

To install Smilee solution to your site you need to register an account at [our agent tool](https://agent.smilee.io){:target="_blank"} and a domain at [admintool](https://agent.smilee.io/admintool){:target="_blank"}.

After registering you can get your script (see example below) from our [admintool](https://agent.smilee.io/admintool) and set it to your site. After this step the Chat will appear on your site. :)

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
  });
</script>
{% endhighlight %}

We suggest you place the script in the footer of your site with rest of the javascript libraries, this way it doesn't affect the loading of the site and gives your customers best possible experience.
