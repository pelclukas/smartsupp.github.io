---
title: "Multilanguage chat box"
subtitle: "Choose a language to fit your business."
description: "Set up different chat box localization for every language mutation of your website."
---

## Chat box language

In this case we setup English using code `en` in our script.

```js
<script>
  smartsupp('language','en');
</script>
```

Supported language codes:

* `ar` = Arabic (U.A.E.)
* `az` = Azeri (Latin) (Azerbaijan)
* `bg` = Bulgarian (Bulgaria)
* `br` = Portuguese (Brazil)
* `ca` = Catalan (Spain)
* `cn` = Chinese Simplified (China)
* `cs` = Czech (Czech Republic)
* `da` = Danish (Denmark)
* `de` = German (Germany)
* `el` = Greek (Greece)
* `en` = English (United States)
* `es` = Spanish (Spain)
* `fa` = Persian = Farsi (Iran)
* `fi` = Finnish (Finland)
* `fr` = French (France)
* `he` = Hebrew (Israel)
* `hi` = Hindi (India)
* `hr` = Croatian (Croatia)
* `hu` = Hungarian (Hungary)
* `is` = Icelandic (Iceland)
* `it` = Italian (Italy)
* `ja` = Japanese (Japan)
* `ka` = Georgian (Georgia)
* `lt` = Lithuanian (Lithuania)
* `lv` = Latvian (Latvia)
* `mk` = Macedonian (FYROM)
* `nl` = Dutch (Netherlands)
* `no` = Norwegian (Norway)
* `pl` = Polish (Poland)
* `pt` = Portuguese (Portugal)
* `ro` = Romanian (Romania)
* `ru` = Russian (Russia)
* `sk` = Slovak (Slovakia)
* `sl` = Slovenian (Slovenia)
* `sr` = Serbian (Latin) (Bosnia and Herzegovina)
* `sv` = Swedish (Sweden)
* `th` = Thai (Thailand)
* `tr` = Turkish (Turkey)
* `tw` = Chinese Traditional (Taiwan)
* `uk` = Ukrainian (Ukraine)

Missing your language? Contact [support@smartsupp.com](mailto:support@smartsupp.com).
{: .callout .callout-info }

## Custom texts

If you want to modify existing texts you can write your own texts in any language. All you need to do is to define the language at the end of the script. In this example we change default text Online => **We are online**.

![we are online](/assets/img/docs/examples/multilanguage-chat-box/we-are-online.png)

```js
<script>
  smartsupp('translate', {
    widget: {
      online: 'We are online'
    }
  }, 'en');
</script>
```

Have a look at [All customizable texts](#all-customizable-texts) at the end of this page.
{: .callout .callout-warning }

## Modify multiple languages

If you have multilanguage website you can modify more languages in the same `.js` file. Expand code below using `conditions` and check your site URL for language code. Based on language you can choose translations you need. In this example you would look for `/en/` or `/de/` in your URL.

* `http://example.com/de/`
* `http://example.com/pl/`
* `http://example.com/en/`

```js
<script>
  if(window.location.href === "http://example.com/de/") {
    smartsupp('translate', {
      widget: {
        online: 'Wir sind hier.'
      }
    }, 'de'); // set DE language
  } else if(window.location.href === "http://example.com/pl/") {
    smartsupp('translate', {
      widget: {
        online: 'Wir sind hier.'
      }
    }, 'pl'); // set PL language
  } else {
    smartsupp('translate', {
      widget: {
        online: 'We are here.'
      }
    }, 'en'); // set EN langauge
  }
</script>
```

## Create new texts

Maybe your language is not on of those we provide. Maybe you do not need everything translated and need just some parts. You can create your own texts and define language code for your own language. Any other words will be added from our default English texts.

```js
<script>
  smartsupp('translate', {
    widget: {
      online: 'Text for language XY.'
    }
  }, 'xy'); // set your own langauge code

  // define the language code
  smartsupp('language','xy');
</script>
```

## Custom Privacy notice

In Dashboard **Settings > Chat box > [Options](https://www.smartsupp.com/app/settings/chatbox/options/){:target='\_blank'}** you can select **Show notice about personal data processing** (visible when offline). In case you do not want default text you can change it.

![privacy notice](/assets/img/docs/examples/multilanguage-chat-box/privacy-notice.png)

```js
<script>
  smartsupp('translate', {
    privacyNotice: {
      title: 'Your Privacy notice title',
      text: 'Custom text'
    }
  });
</script>
```

## All customizable texts

Below are all texts we currently available for customization of your chat box.

You can customize:

* online window
* offline window
* pre-chat form
* chat banners
* chat box
* mobile widget

```js
<script>
  smartsupp('translate', {
    online: { // online window
      title: 'Support',
      infoTitle: 'Live chat',
      infoDesc: 'Ask us anything',
      maximize: 'Maximize',
      minimize: 'Minimize',
      hideTitle: 'Hide chat',
      closeTitle: 'Close chat',
      settingsTitle: 'Settings',
      disableSounds: 'Disable sounds',
      enableSounds: 'Enable sounds',
      visitor: 'Me',
      send: 'Send',
      textareaPlaceholder: 'Write here, press  to send',
      typingMsg: '{name} is typing...',
      transcriptSendingTitle: 'Sending email...',
      transcriptSendingDesc: '',
      transcriptSendedTitle: 'Email was successfully sent',
      transcriptSendedDesc: ''
    },
    offline: { // offline window
      title: 'Send us a message',
      notice: 'We are not available now but leave us a message. We will respond as soon.',
      hideTitle: 'Hide chat',
      required: '',
      name: 'Name',
      email: 'Email',
      number: 'Phone',
      message: 'Your message',
      submit: 'Send message',
      messageRequiredAlert: 'You have not entered a message.',
      emailRequiredAlert: 'You have not entered an email address.',
      emailInvalidAlert: 'Invalid email address',
      sendInfo: 'Sending email...',
      successTitle: 'Thank you for your message',
      successDesc: 'Your message was sent successfully. We will contact you soon.',
      failureTitle: 'Error',
      failureDesc: 'We are sorry but your message wasn\'t sent.'
    },
    login: { // pre-chat form
      title: 'Chat login',
      notice: '',
      messageLabel: 'Your question',
      submit: 'Start chat'
    },
    banner: { // chat banners
      bubble: {
        text: 'We are ready for your questions!'
      },
      arrow: {
        title: 'Any questions?',
        desc: 'We are ready to answer.'
      }
    },
    widget: { // chat box
      online: 'Ask us anything',
      away: 'Ask us anything',
      offline: 'Leave us a message',
    },
    button : { // mobile widget
      title: 'Chat'
    },
    dialogClose: {
      title: 'Would you like to end the conversation?',
      yes: 'Yes',
      no: 'No',
      send: 'Yes, and send chat to email'
    },
    dialogSend: {
      title: 'Send conversation to email',
      email: 'Email',
      yes: 'Send',
      no: 'Cancel'
    },
    dialogRating: {
      title: 'How would you rate the chat?',
      cancel: 'I don\'t want to rate',
      submit: 'Send',
      commentTitle: 'Your comment'
    }
  }, 'en');
</script>
```
