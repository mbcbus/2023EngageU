# 5 Basic JS Techniques

## stringify() 
Used to translate JSON back to FileMaker (opposite is parse() to convert string to JSON).

Example:
```
const obj = {name: "John", age: 30, city: "New York"};
const myJSON = JSON.stringify(obj);
FileMaker.PerformScriptWithOptions('My Script Name', myJSON, '4')
```

Documentation: 
[W3Schools](https://www.w3schools.com/js/js_json_stringify.asp)
[Claris](https://help.claris.com/en/pro-help/content/scripting-javascript-in-web-viewers.html)

## How to concatenate strings
Just how you would use ampersand to join things in FileMaker, it's important to know how to join things together in JS. 

There are actually two easy ways to do this:
```
let text1 = "Hello";
let text2 = "world!";
let text3 = "Have a nice day!";

// Using string class "concat" method
let result = text1.concat(" ", text2, " ", text3);

// Using operator method
let result = text1 + ' ' + text2 + ' ' + text3;
```

Remember, JS is picky about field types, so if you try and concatenate a number to a string, you might get some unexpected results!

Documentation:
[W3Schools](https://www.w3schools.com/jsref/jsref_operators.asp)
[W3Schools](https://www.w3schools.com/jsref/jsref_concat_string.asp)

## Basic operators (comparison, logical)
Comparison operators are used to make "truthy" statements for calculations. 
```
5 == "5"        // equal to value, but type is not considered. This example is true.

5 === "5"       // equal to value or type. This example is false.

5 != "6"        // not equal to value, type is not considered. This example is true.

5 !== "6"       // not equal to value or type. This example is true.

6 > 5           // true
6 < 5           // false
5 >= 5          // true
4 <= 3          // false

6 > 5 && 5 == 6 // && is the AND operator, both conditions must match. This example is false.

6 > 5 || 5 < 4  // || is the OR operator, either statement must match. This example is true.
```

Documentation:
[W3Schools](https://www.w3schools.com/jsref/jsref_operators.asp)

## Array Truthy Methods (length, includes)
More advanced functions can be used on things like JSON arrays.
```
const fruits = ["Banana", "Orange", "Apple", "Mango"];

// array length checking
if (fruits.length > 2) {
    console.log('More than two fruits are present');
}

// includes checking
if (!fruits.includes('Kiwi')) {
    console.log('Time to order more kiwis!');
}
// Note the addition of ! to flip the context.
```

Documentation:
[Mozilla length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length)
[Mozilla includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)

## Basic array methods (find, sort, reverse)
```
const array1 = [5, 12, 8, 130, 44];
const found = array1.find((element) => element > 10);
// Expected output: 12. Note this is the FIRST matching value.

const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
// Expected output: Array ["Dec", "Feb", "Jan", "March"]

const array1 = ['one', 'two', 'three'];
const reversed = array1.reverse();
// Expected output: "reversed:" Array ["three", "two", "one"]
```

Documentation:
[Mozilla Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)