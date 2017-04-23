---
layout: docs
subTitle: Tab
customize: true
---

## Tab customization

### Tab location

You can customize location of the start button to 3 predefined
places with supported positions

* top-right
* bottom-right
* bottom-left

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    tabLocation: ‘bottom-right‘
  });
</script>
{% endhighlight %}

### Auto popoup delay

Auto popup can be set to trigger differently on different sites.
You can have it popping up in shopping cart after 20 seconds to prevent abandonement or you can make it pop up almost instantly when customer arrives to the site. It will pop up only once and if you wish to pop it up again you need to clear smilee-autoPopupDone from sessionStorage by running

{% highlight html linenos %}
sessionStorage.removeItem('smilee-autoPopupDone')
{% endhighlight %}

To set the autopopup timeout in seconds use


{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    autoPopupDelay: ‘15‘
  });
</script>
{% endhighlight %}

### Serving context

You can have different teams serving different parts of the site, for example sales team on sales site and support team on support site, just set the team name to context of the script

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    context: ‘Ultimate sales team'
  });
</script>
{% endhighlight %}
### Hide the tab

With noTab property you can make the tab invisible on certain sites, if you do not wish to show it to visitors.
{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    noTab: true
  });
</script>
{% endhighlight %}

### Start chat from different button
You can start the chat from any button on your site for example with jQuery.click() method.
In this example we run the "tab click" when we click a button with class `open-chat-button`.

Combinig this and the previous step you can run the chat from any button on your site without the normal start chat button.

{% highlight js linenos %}
  $(function() {
    $('.open-chat-button').on('click', function() {
      $('#smilee-request-cobrowsing').click();
    });
  });
{% endhighlight %}

### Online start button

##### Start button title

You can insert custom text to start button. You can also add any icon from [Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/)

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    startButtonTitle: 'Welcome to Smilee!',
    startButtonSymbol: ‘<i class="fa fa-envelope"></i>’,
  });
</script>
{% endhighlight %}

#### Start button color

You can define the background and text colors of the start button by setting the attributes tabTextColor and tabColor
* rgb (rgb(255,255,255))
* hex (#fff)
* string (white)

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    tabTextColor: ‘#FFFFFF’,
    tabColor: ‘black
  });
</script>
{% endhighlight %}

### Offline Start button

#### Hide start button when no agents present

If you don't wish to use offline start button in certain pages you can set the init to remove the button when no agents are found
by setting hiddenWhenNoAgents boolean.

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    hiddenWhenNoAgents: true
  });
</script>
{% endhighlight %}
#### Use different offline button
You can define the offline start button to look different from online start button by setting this boolean value.

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    useOfflineButton: true
  });
</script>
{% endhighlight %}

##### Offline start button title

You can insert custom text to offline start button. You can also add any icon from [Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/)

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    offlineButtonTitle: 'Send us a Message!',
    offlineButtonSymbol: ‘<i class="fa fa-envelope"></i>’,
  });
</script>
{% endhighlight %}

#### Offline start button color

You can define the background and text colors of the offline start button by setting the attributes `offlineButtonTextColor` and `offlineButtonTabColor`
* rgb (rgb(255,255,255))
* hex (#fff)
* string (white)

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    offlineButtonTextColor: ‘#FFFFFF’,
    offlineButtonTabColor: ‘black
  });
</script>
{% endhighlight %}
#### Phone number field on contact form

If you wish you can give customers the phonenumber field in contact form by setting the `contactPhone` boolean.

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    contactPhone: true
  });
</script>
{% endhighlight %}
