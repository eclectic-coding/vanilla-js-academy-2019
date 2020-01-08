# Getting an element in the DOM

You can use the `document.querySelector()` method to find the first matching element on a page. Pass in any valid CSS selector. If an element that matches that selector exists in the DOM, or UI, the `querySelector()` method will return the first matching one.

Grab the first DIV

```javascript
var elem = document.querySelector('div');
```

Get any valid CSS selector:

```javascript
// The first div with a data attribute of snack equal to carrots
var elemCarrots = document.querySelector('[data-snack="carrots"]');
```

`querySelector` will return `null`if the selector does not exist.

Check if the selector exist

```javascript
// Verify element exists before doing anything with it
if (elemNone) {
	// Do something...
	elemNone.id = 'new-id';
}
```

# Adding Event Listeners

Use `addEventListener` to listen for events on and interactions with an element. You can find [a full list of available events on the Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/Events).

```javascript
var btn = document.querySelector('#click-me');

btn.addEventListener('click', function (event) {
	console.log(event); // The event details
	console.log(event.target); // The clicked element
}, false);
```

Event Listeners accepts three arguments:

- Event( IE. `click` )
- Callback method run at the event
- Use capture - optional in newer browsers but it she always be set for cross browser support (normally `false`). Read [here](https://gomakethings.com/when-to-use-use-capture-in-your-event-listeners/) for more clarification

```javascript
btn.addEventListener('click', function (event) {
  console.log('The button is clicked!')
	console.log(event); // The event details
	console.log(event.target); // The clicked element
}, false);
```
More performant for the browser to declare variables outside of the click event.

