# Turboprop

Turboprop provides functionality to modify arrays so that they can be used as property accessors (both for getting values, and setting values). It also lets you define the methods by which the target object's properties are *get* and *set* using the array.

That probably seems a lot like gibberish, so the best way to explain is with some sample code:
```js
// Retrieve multiple values from an array
const arr = ['a', 'b', 'c', 'd', 'e']
console.log(arr[[0, 2, 4]])   // ["a", "c", "e"]

// Nested retrieval
console.log(arr[[0, 2, [3,4]]])   // ["a", "c", ["d", "e"]]

// Setting multiple values in an array
arr[[1, 3, 5]] = ['r', 'h', 's']
console.log(arr)   // ["a", "r", "c", "h", "e", "s"]

// combine getting and setting array values
arr[[0,1]] = arr[[2,0]]
console.log(arr)   // ["c", "a", "c", "h", "e", "s"]


// Retrieve multiple object properties
const obj = {a: 5, b: 6, c: 7, d: 8, e: 9}
console.log(obj[['b', 'c', 'e']])   // [6, 7, 9]

// Set multiple object properties
obj[['a', 'e']] = [33, 66]
console.log(obj)   // { a: 33, b: 6, c: 7, d: 8, e: 66 }


// Retrieve multiple characters from a string
const str = "Hello world!"
console.log(str[[0, 4, 7, 10, 11]])   // 'Hood!'
console.log(str[6[to(10)]])   // 'world' (using 'to' from metho-number)

// Strings are immutable - hence no setting

// More useful(?) examples
const addr = "123 High Street, My Town, My State"
const address = {}
address[['line1', 'line2', 'line3']] = addr.split(',').map(s=>s.trim())
console.log(address)   // { line1: "123 High Street", line2: "My Town", line3: "My State" }

const obj1 = {type: 'box', col1: 'red', col2: 'blue', col3: 'green'}
const obj2 = {}
obj2[['item', 'colours']] = obj1[['type', ['col1', 'col2', 'col3']]
console.log(obj2)   // {item: 'box', colours:['red', 'blue', 'green']}

```

If you would like the above standard behaviours to be added to `Array.prototype` - giving in ANY array gaining the ability to behave like this with other arrays, objects, and strings - simply call `initialiseGlobally()`.




## Why was this built?

Basically I just wanted to see if it was possible to do it. Ever since I wrote [Metho](https://github.com/jonrandy/metho), I've been churning ideas in my head about what other possibilities would be opened up with similar JS syntax hacking. **Turboprop** is the first useful(?) thing to come out of the ensuing experiments.



## How it Works

To do...



## Usage

To do...

