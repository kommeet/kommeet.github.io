---
layout: docs
subTitle: Opening chat
advanced: true
---
# Open chat Options

## Launch chat from different button with different properties

You can open the chat from different buttons by setting a action `getActionTrigger` to options.
In the example below we set the kickOpenFunc to a element with id open-chat.
You can provide email, name and first message for the customer for easier identification in the
agent side. These can also be empty.

We recommend you use `hideTab` option with this to hide the default tab.

{% highlight js linenos %}
<scrip src="https://saas.smilee.io/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  var kickOpenFunc = function(props) {
    console.log('Placeholder kickOpenFunc props:', props);
  };
  var opts = {};
  opts.apiKey = "LQt/yocAfcWRAt...";
  opts.noTab = true;

  $('#open-chat').on('click', function() {
    kickOpenFunc({
      email: $('#e-mail').val(),
      name: $('#my-name').val(),
      firstMessage: 'Interested about Smilee.io Chat!'
    });
  });

  opts.getActionTrigger = function(myCallback) {
    kickOpenFunc = myCallback;
  };

  Cobrowse.create(opts);
</script>
{% endhighlight %}
