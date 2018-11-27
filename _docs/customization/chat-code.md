---
title: "Chat code"
subtitle: "Change modify parts of chat box and its behavior."
description: "Smartsupp chat asynchronous API modifies chat box features, behavior, design, languages, customer info and pre-chat."
---

If you did not install [Smartsupp Chat Code](https://www.smartsupp.com/help/smartsupp-chat-code/){:target='\_blank'} on your site yet read our tutorial first.
{: .callout .callout-info }

## Configuration

You can modify your own chat code. Enter _your configuration_ after the line with `_smartsupp.key` All examples are explained below with screenshots and code samples.

```js
<script type="text/javascript">
  var _smartsupp = _smartsupp || {};
  _smartsupp.key = "YOUR_SMARTSUPP_CODE";
  // ...
  // your configuration
  // ...
  window.smartsupp||(function(d) {
    var s,c,o=smartsupp=function(){ o._.push(arguments)};o._=[];
    s=d.getElementsByTagName('script')[0];c=d.createElement('script');
    c.type='text/javascript';c.charset='utf-8';c.async=true;
    c.src='//www.smartsuppchat.com/loader.js';s.parentNode.insertBefore(c,s);
  })(document);
</script>
```

## Sub-domains integration

Smartsupp visitor is identified by unique key stored in cookies. By default chat conversation is terminated when visitor opens a sub-domain on your website. You should set main domain as cookie domain if you want chat conversations uninterrupted across your sub-domains. Insert the cookieDomain parameter in your chat code on main domain and all subdomains where you want the chat conversation uninterrupted.

```js
_smartsupp.cookieDomain = ".your-domain.com";
```

## Hide chat box on certain pages

You can hide chat box on certain pages by setting the variable `hideWidget` or `hideMobileWidget` in your code.

```js
_smartsupp.hideWidget = true; // use on specific pages
_smartsupp.hideMobileWidget = true; // hide chat box on mobile devices
```

## Privacy notice

You can manually enable or disable privacy notice in chat box. Also you can specify custom url for your own privacy page. This could be useful when you are using Smartsupp chat across several sites.

```js
_smartsupp.privacyNoticeEnabled = false; // privacy notice visibility in chat widget
_smartsupp.privacyNoticeUrl = "https://"; // URL of your privacy page
```

## Custom settings

Use any of these API settings if you want to disable text area and send button, auto messages, sounds for visitors or hide chat bubble.

```js
_smartsupp.writable = false; // text area and send button
_smartsupp.triggerable = false; // auto-messages
_smartsupp.soundMuted = true; // sounds for visitors
_smartsupp.hideBanner = true; // chat bubble
```

## Mobile chat box

This API code allows you to set when to show mobile chat box.

```js
_smartsupp.smallDeviceMinWidth = 641; // screen width in pixels when mobile chat box is shown
```


## Chat box position

By default chat box is displayed in the screen bottom `right` corner. You can change its position.

```js
_smartsupp.alignX = "left";

```

You can change its position also to side.

```js
_smartsupp.alignY = "side";

```

You can also offset chat box if you need using `offsetX` and number sets distance in pixels on the X axis from default position.

```js
_smartsupp.offsetX = 100;
```

Y axis for side possition chat box.

```js
_smartsupp.offsetY = 100;
```
