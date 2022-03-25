## 15 Life-Changing Javascript Hacks

There are many incredible features in javascript that may make your life a lot easier. In this article, I've listed 15 things that every javascript developer should be aware of.

### Change the length of an array
```js
let x = ['Pune', 'Hyderabad', 'Banglore', 'Mumbai', 'Indore', 'Delhi']
console.log(x.length) // OUTPUT 6
x.length = 3
console.log(a) // OUTPUT ['Pune','Hyderabad','Banglore']
``` 

### Swap two variables
```js
let a = 10;
let b = 20;
console.log(a, b) // OUTPUT 10, 20
[a, b] = [b, a]
console.log(a, b) // OUTPUT 20, 10
```

### Concatenating two or more arrays efficiently
```js
// Old way
let x = [1, 2, 3, 4, 5]
let y = [4, 5, 6, 7, 8]
let z = x.concat(y) // creates a new array c and push contents from array and b into array c which will consume a lot of memory
console.log(z) // OUTPUT 1, 2, 3, 4, 5, 4, 5, 6, 7, 8


// New way
let x = [1, 2, 3, 4, 5]
let y = [4, 5, 6, 7, 8]
x.push.apply(x, y) // pushes the content of array b into array a
console.log(x)
```

### Change the way you use a filter
```js
let x = [
	null,
	undefined,
	{ name: 'Alex' },
	{ name: 'Nick' },
	{ name: '' },
	null,
];
let y = x.filter((item) => item.name.length > 0); // not working, this will cause the error TypeError: Cannot read property 'length' of undefined

// we can use a filter with boolean to remove the null and undefined Values

y = x.filter(Boolean).filter((it) => it.name.length > 0);
console.log(y); // OUTPUT
```

### Iterate on the map from 0 to n
```js
const n = 100;
[...Array(n)].map((it, index) => console.log(index));
```


### Replace all occurrences of a word in a string
```js
let str = 'India India USA India UK India';
console.log(str.replace(/India/, 'USA'));
// OUPUT USA India USA India UK India
// Add g at the end of string it will replace all occurences
console.log(str.replace(/India/g, 'USA'));
```

### Exchange types of strings and numbers
```js
// string to number
let x = '123';
console.log(+x); //Output 123
let y = '';
console.log(+y); //NaN

//number to string
x = 123;
console.log(x + '');
```

### Change the way you console log
```js
// %s replaces an element with a string
console.log('Hello I love %s', 'Javascript');
// %d  replaces an element with an integer
console.log('Hello %d ', 1);
// %f  replaces an element with a float
console.log('Hello  %f ', 1.078);
// %(o|O) | element is displayed as an object.
console.log('Hello %O', { Name: 'Sidd' });
// %c | Applies the provided CSS
console.log('%cThis is a red text', 'color:red');
```

### console.table
```js
// we can use console.table to show objects in tabular format
let x = [{ city: 'Banglore' }, { city: 'Pune' }, { city: 'Mumbai' }];
console.table(x);
```
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1648217352172/YcdZj4Qj-.png)


### Retrieve the items from the end of an array
```js
let x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
conosle.log(x.slice(-1)); // [10]
console.log(x.slice(-2)); // [9,10]
```

### Get n power of any number
```js
console.log(2 ** 3); // 8
console.log(2 ** 12); // 4096
```

### Call a function by it's string name using the eval function
```js
const print = () => console.log('hello');
setTimeout(() => eval('print')(), 1000); // hello
```

### typeof operator
```js
// the typeof operator returns a string indicating the type of the unevaluated operand
console.log(typeof 12); // number
console.log(typeof 'hello'); // string
console.log(typeof []); // object
console.log(typeof true); // boolean
console.log(typeof {}); // object
```

### Rest parameters
```js
// the rest parameter syntax allows a function to accept an indefinite number of arguments as an array, it like a variadic function in C
function abc(...args) {
	console.log(args);
}
abc(1); // [1]
abc(1, 2); // [1,2]
abc(1, 2, 3); // [1,2,3]
abc(1, 2, 3, 4); // [1,2,3,4]
```

### Generator functions
```js
// the function* declaration (function keyword followed by an asterisk) defines a generator function, which returns a Generator object.
function* generator(i) {
	yield i;
	yield i + 10;
}

const gen = generator(10);

console.log(gen.next().value); // 10
console.log(gen.next().value); // 20
```

### 

## Conclusion

You've now learnt some important JS hacks for minifying JavaScript code, and some of these approaches are used in popular JS frameworks such as Lodash, Underscore.js, and Strings.js, among others.

I hope you enjoyed my post, and do let me know if you have any more JS hacks to share!