# Read: 09 - Forms and Events

## Content

- [HTML & CSS](#html--css)
  - [Forms](#forms)
  - [Lists, Tables & Forms](#lists-tables--forms)
- [JavaScript](#javascript)
  - [Events](#events)
- [Reference](#reference)

***

## HTML & CSS

### Forms

To retrieve user information, an HTML form is used.

Text Box

```html
<form>
  <input type="text" id="firstName" name="firstName" placeholder="first name">
  <input type="text" id="lastName" name="lastName" placeholder="last name">
</form>
```

Checkboxes

```html
<form>
  <input type="checkbox" id="colorBlack" name="colorBlack" value="Black">
  <label for="vehicle1"> one of my favorite color Black</label><br>
  <input type="checkbox" id="colorRed" name="colorRed" value="Red">
  <label for="vehicle2"> one of my favorite color red</label><br>
  <input type="checkbox" id="colorBlue" name="colorBlue" value="Blue">
  <label for="vehicle3"> one of my favorite color Blue</label>
</form>
```

Radio Buttons

```html
<form>
  <input type="radio" id="male" name="gender" value="male">
  <label for="male">Male</label><br>
  <input type="radio" id="female" name="gender" value="female">
  <label for="female">Female</label>
</form>
```

There is a lot of `forms` in HTML

[Back to Content](#content)

### Lists, Tables & Forms

As we were used to in the past, all elements on the web page can be taken, manipulated, and displayed as you like, as Lists display it as a navbar or Forms for sign up, log in, contact us, exam form, feedback form... etc

[Back to Content](#content)

## JavaScript

### Events

Your browser records various kinds of events as you navigate the site. This is how the browser expresses itself, But, in terms of the event, it's about what you do on the web, what data you gather, and where you'll show it to the user, and in what form.

What does JavaScript have to offer? User feedback and actions can be handled and verified using event handlers.

An HTML event may be initiated by the browser or initiated by the user.

Here are some HTML event examples: [001](#001)

- The loading of an HTML web page is complete.
- A HTML input field has been modified.
- The HTML button was pressed.
- When events occur, you may feel compelled to act.

When events are found, JavaScript allows you to run code.

[Back to Content](#content)

## Reference

### 001
W3schools.com. (2015). JavaScript Events. [online] Available at: [link](https://www.w3schools.com/js/js_events.asp) [Accessed 23 Mar. 2021].


***

[⇐ Home Page](../README.md)
