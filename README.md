# Kommeet documentation

**Attention!** Using custom init options overwrite anything chosen in the dashboard! All of these methods, attribures and hacks are subject to change and may be deprecated with one month of notice!

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

## Fetch/Push info from client to agent

Currently you can push information such as name or address information. This information will be shown
in agent as context in userinfo panel. *Host address needs to match one of the domain urls in Kommeet service*

#### Fetch info
Fetching is done with adding options to script.

```
  uid: {
    doFetch: true,
    url: 'https://host/path?args#hash'
  }
```

And data expected from the fetch is expected to be in form
```
{
  name: 'Hemmo Hemminki',
  url: 'https://host/profile-info-path'
}
```


```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    uid: {
      doFetch: true,
      url: 'https://host/path?args#hash'
    }
  });
</script>
```

#### Push info

Info can also be pushed with script options in form of

`uid: 'Hemmo Hemminki'` Will result in showing context as a string
`uid: 'https://host/path?args#hash'` Will result showing context as a link


Option underneath will result in showing context string as a clickable link
```
uid: {
    name: 'Hemmo Hemminki',
    url: 'https://host/profile-info-path'
  }
```


Example script:
```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    uid: 'Hemmo Hemminki'
  });
</script>
```


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
### Hide the tab

With noTab property you can make the tab invisible on certain sites, if you do not wish to show it to visitors.
```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    noTab: true
  });
</script>
```

### Start chat from different button
You can start the chat from any button on your site for example with jQuery.click() method.
In this example we run the "tab click" when we click a button with class `open-chat-button`.

Combinig this and the previous step you can run the chat from any button on your site without the normal start chat button.

```
  $(function() {
    $('.open-chat-button').on('click', function() {
      $('#kommeet-request-cobrowsing').click();
    });
  });
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

You can define the background and text colors of the offline start button by setting the attributes `offlineButtonTextColor` and `offlineButtonTabColor`
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

If you wish you can give customers the phonenumber field in contact form by setting the `contactPhone` boolean.

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    contactPhone: true
  });
</script>
```

## Chat box customizations

### Welcome texts

You can set different welcome texts on different pages by using the attribute welcomeTitle and welcomeText.

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    welcomeTitle: 'Hello there!',
    welcomeText: 'That is a nice looking coat!'
  });
</script>
```

### Agents are busy texts and timing

You can set the timing when the customer will get agents are busy message, this will prevent customers waiting in line for too long. This timer starts when customer sends first message and is cleared when agent joins the session. Use `feedbackButtonDelay` to set the delay to offer `feedbackform` and `maxAgentWaitTime` to force customer to use feedbackform. These timers are in seconds.

You can also customize the message the customer receives.

```
<scrip src="https://saas.kommeet.com/assets/javascripts/cobrowse.js" charset="UTF-8"></script>
<script>
  Cobrowse.create({
    apiKey: "LQt/yocAfcWRAt...",
    waitingForAgentMsg: 'All of our agents are busy, you can also',
    waitingForAgentBtn: 'send us a message!',
    feedbackButtonDelay: 60,
    maxAgentWaitTime: 120,
  });
</script>
```
