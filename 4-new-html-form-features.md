---
layout: default
title: New HTML form features
---

# New HTML form features

## Input types

A new set of `input` types were added to HTML to offer improved semantics, accessibility, and User Experience (UX). They do this mostly by replacing custom, usually heavy, JavaScript solutions with things closer to the browser.

### Make things a little better

`email` and `url` `input` types are for email addresses and web addresses, respectively. They offer validation, helping users enter correct information.

`number` and `tel` are for numbers and telephone numbers. `number` can have `min`, `max`, and `step` attributes. These also offer validation, helping users enter correct information. These are particularly noticable on mobile devices, where the displayed keyboard changes: `number` or `tel` can trigger the numerical keyboard rather than the standard alphanumeric one.

Here's an example with the new input types: [form-easier.html](form-easier.html)

```html
<form action="/" method="post">
    <fieldset>
        <legend>Your info</legend>

        <label>Your email<br />
        <input type="email" name="your-email">
        </label>
        <label>Your URL<br />
        <input type="url" name="your-url" value="https://">
        </label>

        <button type="submit">Send the data</button>
    </fieldset>
</form>
```

What happens if you don't enter a correctly formatted email address or URL? Why did we add `value="https://"` and what happens if we remove it?

### Going native

Some of the new HTML form elements "pave the cowpaths" and give the browser native ways of providing some of features that used to only be possible with lots of JS.

JS date pickers can be replaced by `<input type="date" />`. JS sliders can be replaced by `<input type="range" />`. Both of these accept `min` and `max` attributes, and range accepts `step`. Elaborate JS colour pickers can be replaced by `<input type="color" />`.

JS is still needed to for some client-side updates (such as live-updating the selected value of a `range`), but the form control itself comes from the browsers. This is better because these types of inputs can now render more consistently across sites in terms and look & feel and operation. It also reduces the amount of code you need to write since the browser is handing the form control for you.

TODO: add example.

## Helper attributes

On top of the new `input` `type`s, some new attributes where added to further help with UX.

The `required` attribute is probably the most widely used. It replaces JS checks for whether or not a field has been filled out.

The `placeholder` attribute adds "ghost text" as an extra hint to the user. This should only be used as additional information, and usually takes the form of an example. The `input`s label should make the desired input clear to the user.

The `pattern` attribute allows for validation on the input based on the supplied a Regular Expression. RegEx is very powerful, so this can be very useful. It can also be very complicated, though!

Another useful, but potentially evil attribute is `autofocus`. This brings the user's brings the focus of the page to the `input` with the `autofocus` attribute on. This can be more annoying than helpful, so be very sure that it will help your users more than hinder them!

TODO: add example.
