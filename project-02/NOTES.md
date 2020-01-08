# Getting multiple elements in the DOM

You can use the `document.querySelector()` method to find the first matching element on a page. Pass in any valid CSS selector. If an element that matches that selector exists in the DOM, or UI, the `querySelector()` method will return the first matching one.

Grab the first DIV

```javascript
// Get all elements with the .bg-red class
var elemsRed = document.querySelectorAll('.bg-red');

// Get all elements with the [data-snack] attribute
var elemsSnacks = document.querySelectorAll('[data-snack]');

```

### Browser Compatibilty
This works in all modern browsers, and IE9 and above. It can also be used in IE8 with CSS2.1 selectors (no CSS3 support).

**CSS3 not supported in IE8**

# Looping Over Elements

- Using an ES5 method `forEach` to loop over arrays
- Nodelist are not arrays
  - `Nodelist.for` has poor browser support
- You can convert NodeLists into Arrays by passing them into Array.prototype.slice.call(), which will apply the Array.slice() method to other array-like objects.

```javascript
var sandwiches = Array.prototype.slice.call(document.querySelectorAll('.sandwiches'));
sandwiches.forEach(function (sandwich, index) {
	console.log(sandwich.textContent);
});
```
