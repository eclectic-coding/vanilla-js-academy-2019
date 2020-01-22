# Getting multiple elements in the DOM

You can use the `document.querySelector()` method to find the first matching element on a page.

```javascript
// Get all elements with the .bg-red class
var elemsRed = document.querySelectorAll('.bg-red');

// Get all elements with the [data-snack] attribute
var elemsSnacks = document.querySelectorAll('[data-snack]');

```

### Browser Compatibility
This works in all modern browsers, and IE9 and above. It can also be used in IE8 with CSS2.1 selectors (no CSS3 support).

**CSS3 not supported in IE8**

# Looping Over Elements

- Using an ES5 method `forEach` to loop over arrays
- NodeList are not arrays
  - `Nodelist.forEach` has poor browser support
- You can convert NodeLists into Arrays by passing them into Array.prototype.slice.call(), which will apply the Array.slice() method to other array-like objects.

```javascript
var sandwiches = Array.prototype.slice.call(document.querySelectorAll('.sandwiches'));
sandwiches.forEach(function (sandwich, index) {
	console.log(sandwich.textContent);
});
```

# Author's Solution

```javascript
// Get the password field and toggle checkbox
var passwords = Array.prototype.slice.call(document.querySelectorAll('[type="password"]'));
var toggle = document.querySelector('#show-passwords');
// Listen for click events on the toggle
toggle.addEventListener('click', function (event) {
	// Loop through each password field
	passwords.forEach(function (password) {
		// If the toggle is checked, change the type to "text"
		// Otherwise, change it back to "password"
		if (toggle.checked) {
			password.type = 'text';
		} else {
			password.type = 'password';
		}
	});
}, false);
```
