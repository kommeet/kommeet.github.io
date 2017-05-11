---
layout: docs
subTitle: Fetch and push info
advanced: true
---
# Fetch and push
## Fetch/Push info from client to agent

You can push information such as name or address information. This information will appear in agent as context in userinfo panel. *Host address needs to match one of the domain urls in Smilee service*

This API accepts JSON and if it receives empty values or errors agent will fallback to default view without crashing

#### Fetch info
Fetching happens with adding options to script.

{% highlight json linenos %}
  uid: {
    doFetch: true,
    url: 'https://host/path?args#hash'
  }
{% endhighlight %}

And data expected from the fetch needs to be in form
{% highlight json linenos %}
{
  name: 'Hemmo Hemminki',
  url: 'https://host/profile-info-path'
}
{% endhighlight %}


{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    uid: {
      doFetch: true,
      url: 'https://host/path?args#hash'
    }
  });
</script>
{% endhighlight %}

#### Push info

Pushing happens with script options in form of

`uid: 'Hemmo Hemminki'` Will result in showing context as a string
`uid: 'https://host/path?args#hash'` Will result showing context as a link


Option underneath will result in showing context string as a clickable link
{% highlight json linenos %}
uid: {
  name: 'Hemmo Hemminki',
  url: 'https://host/profile-info-path'
}
{% endhighlight %}


Example script:
{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    uid: 'Hemmo Hemminki'
  });
</script>
{% endhighlight %}
