## Notes


#### Converting String to Array

Using the `split()` method with the first argument as a `delimiter` you can split a string into a new Array:

```javascript
var shoppingList = 'Soda, turkey sandwiches, potato chips, chocolate chip cookies';

var menu = shoppingList.split(', ');

console.log(menu);
```
The `split()` method also accepts a second argument to limit the array.

```javascript
var shoppingList = 'Soda, turkey sandwiches, potato chips, chocolate chip cookies';

var limitedMenu = shoppingList.split(', ', 2);

console.log(limitedMenu);

```

#### Filtering an Array
The `Array.filter()` method is very similar to `Array.find()`. It filters the current array and is non-destructive.

```javascript
// Create a new array with only numbers greater than 10
var newArray = [1, 2, 7, 42, 99, 101].filter(function (item) {
	return item > 10;
});

// logs [42, 99, 101]
console.log(newArray);
```
