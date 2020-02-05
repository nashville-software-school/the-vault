# My Array Functions

JavaScript [arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) are a powerful tool for building complex applications. Along with the ability to store sequential data, the good people at [TC39](https://tc39.es/) have given us many useful array methods to make our lives easier. There are methods for modifying, looping over, transforming, sorting, querying and filtering arrays.

While array methods make it a LOT easier to use arrays, most of the things array methods do could be done with more _low level_ JavaScript code. For example, if you wanted to write a function that did the same things as the array [filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) method, you might write something like this.

```js
function myFilter(array, condition) {
  const result = [];
  for (let i = 0; i < array.length; i++) {
    const element = array[i];
    if (condition(element, i)) {
      result.push(element);
    }
  }
  return result;
}
```

And you could use it like this

```js
const myArray = [100, 1, 200, 2, 300, 3];
const filtered = myFilter(myArray, (num) => num < 100);

console.log(filtered);
// [1, 2, 3]
```

## The Exercise

Write your own "myXXX" functions to mimic the behavior of the following array methods.

* forEach()
* map()
* includes()
* some()
* every()
* find()
* indexOf()
* lastIndexOf()
* join()
* concat()
* reduce()
* reverse()

> **NOTES:** <br/>
> Do not use any array methods in your functions.<br/>
> See [this link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) for a description of what the methods do.