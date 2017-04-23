---
layout: docs
subTitle: Language
customize: true
---
## Language settings

### locale

You can set the init language with inserting the value inside a
a locale which can be calculated from the address for Example

#### Supported

* eng
* fin

#### Example script to get the Language
Address used in this example is www.smilee.io/fi

{% highlight js linenos %}
var pathArray=window.location.pathname.split('/');
var language=pathArray[1];
var lang;
if(language==='en') {
  lang='eng';
  } else {
  lang='fin';
}
{% endhighlight %}

Then the init script

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    locale: lang
  });
</script>
{% endhighlight %}

This will result in usage of finnish language when launching the chat.
