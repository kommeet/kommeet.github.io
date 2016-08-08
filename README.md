# Kommeet documentation

Attention! Using custom init options overwrite anything chosen in the dashboard!

If you find outdated information, think something isn't covered here or want to add some cool trick that you use please
don't hesitate to [contact us through our chat on our site](https://www.kommeet.com)!

These options will let you customize the look and feel of the
Kommeet chat.

## Language settings

### locale

You can set the init language with inserting the value inside a
a locale which can be calculated from the address for Example

#### Supported

* eng
* fin

#### Example script to get the Language
Address used in this example is www.kommeet.com/fi

```
var pathArray=window.location.pathname.split('/');
var language=pathArray[1];
var lang;
if(language==='en') {
  lang='eng';
  } else {
  lang='fin';
}
```

Then the init script

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    locale: lang
  });
</script>
```

This will result in usage of finnish language when launching the chat.

## Tab customization

### Tab location

You can customize location of the start button to 3 predefined
places with supported positions

* top-right
* bottom-right
* bottom-left

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    tabLocation: ‘bottom-right‘
  });
</script>
```

### Auto popoup delay

Auto popup can be set to trigger differently on different sites.
You can have it popping up in shopping cart after 20 seconds to prevent abandonement or you can make it pop up almost instantly when customer arrives to the site. It will pop up only once and if you wish to pop it up again you need to clear kommeet-autoPopupDone from sessionStorage by running

```
sessionStorage.removeItem('kommeet-autoPopupDone')
```

To set the autopopup timeout in seconds use


```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    autoPopupDelay: ‘15‘
  });
</script>
```

### Serving context

You can have different teams serving different parts of the site, for example sales team on sales site and support team on support site, just set the team name to context of the script

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    context: ‘Ultimate sales team'
  });
</script>
```

### Online start button

##### Start button title

You can insert custom text to start button. You can also add any icon from [Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/)

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    startButtonTitle: 'Welcome to Kommeet!',
    startButtonSymbol: ‘<i class="fa fa-envelope"></i>’,
  });
</script>
```

#### Start button color

You can define the background and text colors of the start button by setting the attributes tabTextColor and tabColor
* rgb (rgb(255,255,255))
* hex (#fff)
* string (white)

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    tabTextColor: ‘#FFFFFF’,
    tabColor: ‘black
  });
</script>
```

### Offline Start button

#### Hide start button when no agents present

If you don't wish to use offline start button in certain pages you can set the init to remove the button when no agents are found
by setting hiddenWhenNoAgents boolean.

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    hiddenWhenNoAgents: true
  });
</script>
```
#### Use different offline button
You can define the offline start button to look different from online start button by setting this boolean value.

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    useOfflineButton: true
  });
</script>
```

##### Offline start button title

You can insert custom text to offline start button. You can also add any icon from [Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/)

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    offlineButtonTitle: 'Send us a Message!',
    offlineButtonSymbol: ‘<i class="fa fa-envelope"></i>’,
  });
</script>
```

#### Offline start button color

You can define the background and text colors of the offline start button by setting the attributes offlineButtonTextColor and offlineButtonTabColor
* rgb (rgb(255,255,255))
* hex (#fff)
* string (white)

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    offlineButtonTextColor: ‘#FFFFFF’,
    offlineButtonTabColor: ‘black
  });
</script>
```
#### Phone number field on contact form

If you wish you can give customers the phonenumber field in contact form by setting the contactPhone boolean.

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    contactPhone: true
  });
</script>
```
