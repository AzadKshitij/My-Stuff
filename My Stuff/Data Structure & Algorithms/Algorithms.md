## Find the Symmetric Difference
- Reduce
	- Initially it takes input from array 2 at a time sequential 
	- Return the output of first two and works the way forward.

## Inventory Update
 - localeCompare
	 - Compares two strings locally 
	 - return the order of sort b/w two string
	 - -1 = before; 0 = equal; 1 = after
	 ```javascript
	let text1 = "ab";
	let text2 = "cd";
	let result = text1.localeCompare(text2); // -1

	// To use in an array
	var mylist = [ [1, 'c'], [3, 'a'],  [5, 'b']];
	mylist.sort(function(a,b){return a[1].localeCompare(b[1]);});
```

