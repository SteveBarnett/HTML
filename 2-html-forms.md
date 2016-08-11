---
layout: default
title: HTML forms
---

# HTML forms

HTML forms are a way to gather data and send it to a server to be processed. Popular servers are Nginx and Apache. The server will have an application written in Node.JS, Ruby, Python, PHP, or some other language that does the processing.

A `form` element needs an `action` attribute (what URL should the data be sent to?) and a `method` (which HTTP protocol should it use: GET or POST?). A GET is a request for a resource like a web page or a CSS file. A POST is a request to look at the data and respond accordingly.

```html
<form action="/" method="post">
  <!-- Form controls go here -->
</form>
```

## Form controls

Form controls like `input`s are used to enter data, and `button`s are used to submit the form. Here's [an example of a short form](form-1.html).

```html
<form action="2-html-forms.html#form-controls" method="post">
  <input type="text" name="first-name">
  <button type="submit">Send the data</button>
</form>
```

The `name` attribute is the how the piece of data will be identified by the server.

For improved accessibility (identifying what the control is for) and UX (click anywhere on the label to bring focus to the control) you can use `label`s. You can:

* put the `input` inside the `label` or
* put the `label` near the `input` and use a `for` attribute on the label. The value of the `for` attribute must matches the `id` of an `input`.

Here's [a slightly larger example](form-2.html) showing the two ways to use labels, and introducing a new control: `textarea`, for larger pieces of text.

```html
<form action="2-html-forms.html#form-controls" method="post">
  <label>First Name<br >
    <input type="text" name="first-name" id="first-name">
  </label>
  <br />

  <label for="last-name">Last Name</label><br />
  <textarea name="last-name" id="last-name">
  </textarea>
  <br />

  <button type="submit">Send the data</button>
</form>
```

Other `input`s to look at include `password` and `hidden` types.

### Pick one

When you want your user to pick from some options, rather than type something in, you have a few controls to choose from. If the user should pick more than one thing, use a `checkbox`. If they should pick only one thing, use a `radio` or a `select`.

To improve the logical grouping of your form, and improve UX and accessiblity, you can use:

* the `fieldset` element to group controls;
* the `legend` element to add a description for each group.

Here's [an example](form-3.html) showing these new controls.

```html
<form action="2-html-forms.html#pick-one" method="post">

  <fieldset>
    <legend>What is your favourite animal?</legend>

    <label>Cats
      <input type="checkbox" name="favourite-animal-cats">
    </label>

    <label>Dogs
      <input type="checkbox" name="favourite-animal-dogs">
    </label>

    <label>Fish
      <input type="checkbox" name="favourite-animal-fish">
    </label>
  </fieldset>

  <br />

  <fieldset>
    <legend>Is this a question?</legend>
    <label>Yes
      <input type="radio" name="question" value="Yes">
    </label>
    <label>No
      <input type="radio" name="question" value="No">
    </label>
  </fieldset>
  <br />

  <label>Is this also a question?<br />
    <select name="also-question">
      <option>Yes</option>
      <option>No</option>
    </select>
  </label>
  <br />
  <br />

  <button type="submit">Send the data</button>
</form>
```

Note the use of `name` and `value` across the different `input`s. The `name` identifies what piece of data that will be sent to the server. The `value` is the content of the data that will be sent to the server.

* Each `checkbox` has a separate `name`. You can optionally add a `value`.
* On a `radio` the `name` has to be the same across the options to make sure only one can be picked.
* The `option`s of a selection use their content as the value, unless explicitly set a `value`.

It's a good idea to add `:focus` styles so that you can easily see which form control is active.
