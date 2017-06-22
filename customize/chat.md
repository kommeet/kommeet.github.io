---
layout: docs
subTitle: Chat
customize: true
---
# Chat box customizations

### Welcome texts

You can set different welcome texts on different pages by using the attribute welcomeTitle and welcomeText.


{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    welcomeTitle: 'Hello there!',
    welcomeText: 'That is a nice looking coat!'
  });
</script>
{% endhighlight %}


### Agents are busy texts and timing

You can set the timing when the customer will get agents are busy message, this will prevent customers waiting in line for too long. This timer starts when customer sends first message and dissapears when agent joins the session. Use `feedbackButtonDelay` to set the delay to offer `feedbackform` and `maxAgentWaitTime` to force customer to use feedbackform. These timers are in seconds.

You can also customize the message the customer receives.

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    waitingForAgentMsg: 'Our agents are busy, you can also',
    waitingForAgentBtn: 'send us a message!',
    feedbackButtonDelay: 60,
    maxAgentWaitTime: 120
  });
</script>
{% endhighlight %}

### Increase/Decrease chatbox or fontsize

You can enable increasing/decreasing of enduser chatbox/fontsize with adding new selector in the init script, these selectors are `fontSizeSelector` and `chatSizeSelector`. Note that you can use one of these, not both!

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    chatSizeSelector: true
  });
</script>
{% endhighlight %}


### Convert any links to a clickable link

Currently chat converts only links that belong to the domains of the apikey into clickable links. Adding flag `acceptAllUrls` will convert any links into a clickable links which open in a new tab. This is done in order to prevent sending malicious links to customers in accident etc.

{% highlight html linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    acceptAllUrls: true
  });
</script>
{% endhighlight %}