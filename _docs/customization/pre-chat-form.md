---
title: "Pre-chat form"
subtitle: "Make conversations easier for your support staff."
description: "When chat is online visitor can write a message. Pre-chat form will show right after visitor sends first message."
---

## Hide pre-chat form

If you are using pre-chat form, you can hide it on certain pages by setting the variable `requireLogin` in your code.

```js
_smartsupp.requireLogin = false;
```

## Default inputs

If you are using pre-chat form, you can customize the form fields. Default inputs are `name`, `email`. If you want to disable any of them, set property `loginNameControl` or `loginEmailControl` to `false`.

Hide default input: `name`

```js
_smartsupp.loginNameControl = false;
```

Hide default input: `email`

```js
_smartsupp.loginEmailControl = false;
```

## Custom fields

You can add custom fields by setting property `loginControls`. All filled values are sent to dashboard and displayed in **Visitor info** on the right side of chat panel.

- We support 3 field types: `textinput`, `select` and `checkbox`.
- Use attribute `required: true` to make the field mandatory for visitors.
- Attribute `name` must be defined in every field and it can contain only lowercase and uppercase letters, no spaces allowed.

Attribute `name` _is not_ the visible **Name** input but a description of custom field in the code. It can be `name: "phone"` or `name: "group"` or `name: "conditons"` as you will see in examples below.

## Pre-chat form default

You can turn this option on in **Smarstupp Dashboard > Chat box > [Options](https://www.smartsupp.com/app/settings/chatbox/options){:target='\_blank'} > Show pre-chat form**

![pre-chat form default](/assets/img/docs/customization/pre-chat-form/pre-chat-form-default.png)

## Pre-chat form with textinput

This field can be used for example for entering phone number.

```js
_smartsupp.loginControls = [
  {
    xtype: "textinput",
    name: "phone",
    label: "Phone number",
    required: true
  }
];
```

![pre-chat form default](/assets/img/docs/customization/pre-chat-form/pre-chat-form-with-text-input.png)

## Pre-chat form with select

You can use this customization if you have more groups (departments) like: _Support, Marketing, Sales_, etc.

![pre-chat form with select](/assets/img/docs/customization/pre-chat-form/pre-chat-form-with-select.png)

```js
_smartsupp.loginControls = [
  {
    xtype: "select",
    name: "group",
    label: "Department",
    required: true,

    // use group IDs from Smartsupp dashboard
    value: "PJxWeH8LZNi", // set default group
    items: {
      "PJxWeH8LZNi": "Support",
      "tuZOw6k9Oto": "Marketing",
      "9OtIZKLaVep": "Sales"
    }
  }
];
```

## Pre-chat form with checkbox

This can be useful in case you need your visitors to confirm something before they start chat.

![pre-chat form with checkbox](/assets/img/docs/customization/pre-chat-form/pre-chat-form-with-checkbox.png)

```js
_smartsupp.loginControls = [
  {
    xtype: "checkbox",
    name: "conditions",
    label: "I have read the Terms and conditions.",
    required: true
  }
];
```
