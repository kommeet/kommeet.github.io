---
layout: docs
subTitle: CSS
customize: true
---
# Custom CSS

## Customize tab with your own CSS

You can customize tab with your own css to blend in to your site.
Target `#smilee-request-cobrowsing` for tab position, color, shape etc and `#smilee-welcome-text` for custom text properties such as color, font etc.

Chat customization is more limited. You can target it with `#smilee-cobrowsing-frame` and set location and size for example.

Remember to use `!important` in the CSS to overwrite the original CSS set in Smilee application

## Examples

### Customize position of chatbox with CSS
You can customize the position of chatbox with altering the property `#smilee-cobrowsing-frame`. These customizations can be bottom, left, right etc. Use `!important` to overwrite the original CSS.

### Customize size of chatbox and tab with CSS
Size of chatbox when opened is altered with adding style tag to head of your site which targets the correct elements `#smilee-cobrowsing-frame` for chat and `#smilee-request-cobrowsing` for tab. Use `!important` to overwrite the original CSS.

{% highlight html linenos %}
<style>
   #smilee-cobrowsing-frame {transform: scale(1.2) !important;}
   #smilee-request-cobrowsing {transform: scale(1.2) !important; right: 20px;}
</style>
{% endhighlight %}
