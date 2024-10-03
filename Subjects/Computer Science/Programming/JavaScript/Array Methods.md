# Array Methods

## `.map()`

- This method takes a callback function as an argument, executes the function on each value in the array, then returns the modified array.

```javascript
function OneHotEncoder(value, index, array) {
	console.log(`Evaluating index ${index} of ${array}`);
	if (value == true) {
		return 1;
	}
	return 0;
}

[true, false].map(OneHotEncoder)
```

## `.filter()`

- This method takes a callback function as an argument, executes the function on the array, and returns a new array of values that pass the callback function's conditions.

```typescript
function AgeFilter(value, index, array): boolean {
	console.log(`Evaluating index ${index} of ${array}`);
	if (value > 65) or (value < 18) {
		return false;
	}
	return true;
}

[10, 50, 90].filter(AgeFilter)
```