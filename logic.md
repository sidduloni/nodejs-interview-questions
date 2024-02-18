[Go to Nodejs FAQs](https://github.com/sidduloni/nodejs-interview-questions)
----
#Nodejs-logical-interview-questions
#problem-solving-interview-questions-nodejs


## S.No 1 Write callback function and its promise function.
**Ans**
```javascript
// Normal callback function
function asyncOperation(callback) {
    setTimeout(function() {
        callback("Callback executed");
    }, 3000)
}

function callbackFunc(message) {
    console.log(message)
}
asyncOperation(callbackFunc) // We will not use () here

// Promise callback function
  const myPromise = new Promise((resolve, reject) => {
      setTimeout(function() {
          resolve("Promise callback executed")
      },4000)
  })

  myPromise.then((result) => {
      console.log("Promise resut: ", result)
  }).catch((error) => {
      console.log("promise error:", error)
  })
```

## S.No 2 Write Event emmiter example
**Ans**
```javascript

const EventEmitter = require('events');

// Initializing event emitter instances
var eventEmitter = new EventEmitter();

// Registering to myEvent
eventEmitter.on('myEvent', (msg) => {
console.log(msg);
});

// Triggering myEvent
eventEmitter.emit('myEvent', "First event");
```

## S.No 3 How to handle error without using try-catch
**Ans:** Using promises reject callback method we can handle errors
```javascript

async function check2(req, res) {
  try {
    const a = await functionA();
    const b = await functionB();
    res.send("result")
  } catch (error) {
    res.send(error.stack);
  }
}

const check = new Promise((resolve, reject) => {
 return reject("Error encountered!");
}) 

check.then((success) => {
  console.log("If success")
}).catch((error)=> {
  console.log(error);
})
```

## S.No 4 Write a async function which should wait until promise resolve
**Ans:**
```javascript
function one() {
  console.log("one");
}

function delay() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log('two');
      resolve('Delay resolve');
    }, 0);
  });
}

async function two() {
  await delay().then((res)=>console.log(res));
  one(); // This function waits until the delay() promise resolved. Note: Waits within the scope, but not outside methods, properties.
  return 'Function two executed';
}

console.log(3);
two().then((item)=>console.log(item))
console.log(4);

// Output:

// 3
// 4
// two
// Delay done
// one
// Function two executed
```

## S.No 5 Write a prototype or polyfill similar to map, reduce, forEach and filter in javascript
**Ans:**
```javascript
// Map polyfill
Array.prototype.myMap = function(callback) {
 let emptyArr = [];
 for (let i=0; i < this.length; i++) {
   emptyArr.push(callback(this[i], i, this))
 }
 return emptyArr;
}

let sm = [3, 2]
let result = sm.myMap((num) => num + num) // [ 6, 4 ]
// let result = sm.myMap((num) => num.toString()) // [ '3', '2' ]
// let result = sm.myMap((num, index) => num + index) // [ 3, 3 ]
console.log(result)

// Filter prototype
Array.prototype.myFilter = function (cb) {
  let temp = [];
  for (let i = 0; i < this.length; i++) {
    if (cb(this[i], i, this)) temp.push(cb(this[i]));
  }
  return temp;
};
const arr = [2, 3, 4, 5];
console.log("arr", arr);
const data = arr.filter((num) => {
  return num > 2;
});
console.log("Filter Result", data);

// Reduce polyfill
Array.prototype.myReducer = function(cb, initialValue) {
    let accumulator = initialValue;
    for (i = 0; i < this.length; i++) {
        accumulator = accumulator ? cb(accumulator, this[i], i, this) : this[i];
    }
    return accumulator;
};
const arr1 = [2, 3, 4, 5];
const sumOfArray = arr1.myReducer((accu, curr, index, arr) => {
    return (accu += curr);
}, 0);
console.log("polyfil", sumOfArray);

// forEach polyfill
Array.prototype.myForEach = function (callback, thisArg) {
    for (let i = 0; i < this.length; i++) {
        callback.call(thisArg || null, this[i], i, this);
    }
};
// Example usage
var arr = [1, 2, 3];

arr.myForEach(function (element, index, array) {
    console.log(element);
});

// Output:
1
2
3


```

## S.No 6 Write a program to convert first letter uppercase for the given string
**Ans:**
```javascript 

function toTitleCase(str) { 

  return str.replace(/\b\w/g, l => l.toUpperCase()); 

} 
console.log("Title case: ", toTitleCase("hello dude")) // Output: Hello Dude
```

## S.No 7: Write a program to print 1-10 without using loop
**Ans**
```javascript
function noLoop(start, end) {
    if(start <= end) {
    console.log(start)
     noLoop(start+1, end)
    }
  }
  noLoop(1, 10)
```

## S.No 8: Write a program to display sum of square of an odd numbers
**Ans**
```javascript
let a=[1,2,3,4,5,6,7,8,9,10]

const sumOfSquaresOfOddNumbers = a.reduce((sum, num) => {
  if (num % 2 !== 0) {
    return sum + num * num;
  }
  return sum;
}, 0);

console.log('Sum of squares of odd numbers:', sumOfSquaresOfOddNumbers);

```

## S.No 9: Add two numbers using recursion 
**Ans**
```javascript
function add2(a,b) {
  if(b == 0) {
    return a
  } 
  return add2(a + 1,b - 1)
}
console.log("Add Recursion :", add2(10,2))
```

## S.No 10: Merge two unsorted arrays into one sorted array with no duplicates and sort ascending order
**Ans**
```javascript

let arr1 = [2, 6, 44, 12, 34, 44]
let arr2 = [90, 55, 22, 4, 1, 55, 8]

// Or simply use let merged = [...arr1, ...arr2]

let sortedArray = [];
let countOfArray = arr1.length + arr2.length
console.log(countOfArray)

for(let i = 0; i< arr1.length; i++) {
  if(!sortedArray.includes(arr1[i])) {
    sortedArray.push(arr1[i])
  }
}

for(let i = 0; i< arr2.length; i++) {
  if(!sortedArray.includes(arr2[i])) {
    sortedArray.push(arr2[i])
  }
  
}

for(let i=0; i < sortedArray.length; i++) {
  for(let j= 0; j< sortedArray.length - 1; j++) {
    if(sortedArray[j] > sortedArray[j+1]) {
    const temp = sortedArray[j]
          sortedArray[j] = sortedArray[j+1]
          sortedArray[j+1] = temp
    }
  }
}

console.log(sortedArray)
```

## S.No 11:  Given a string, that contains a special character together with alphabets (‘a’ to ‘z’ and ‘A’ to ‘Z’), reverse the string in a way that special characters are not affected.
**Ans**
```javascript
// Input:   str = “a,b$c”
// Output:  str = “c,b$a”

let str2 = 'a,b$c'
let str = str2.split('')
function isAlpa(char) {
  return /[a-zA-Z\s]/.test(char)
}

let left = 0;
let right = str.length - 1

while(left < right) {
  if(!isAlpa(str[left])) {
    left++
  } else if(!isAlpa(str[right])) {
    right--
  } else {
    let temp = str[left]
    str[left] = str[right]
    str[right] = temp
    left++
    right--
  }
  // return str
}

console.log(str.join(''))

let repl = 'My @Home';

let result = repl.replace(/[a-z]+/gi, function(s){
  return s.split('').reverse().join('')
})

console.log(result)
// Output yM @emoH
```

## S.No 12 Write a program to convert value to index
**Ans**
```javascript
let vi = {a:2, c:4}
let emptyObj = {}
for(let obj in vi) {
    emptyObj[vi[obj]] = obj
}
console.log('Value to index : ', emptyObj)
```

## S.No 13 Input "H#e#ll(o$p" Output "#2(1$1"
**Ans:**
```javascript
let str = "H#e#ll(o$p";

let empty = {}

function isSpecialChar(char) {
  return /[^a-z0-9]/gi.test(char)
}
for(let ob of str) {
  if(isSpecialChar(ob)) {
    empty[ob] = (empty[ob] || 0) + 1
  }
}
let output = '';
for(let ob in empty) {
  output += ob + empty[ob]
}
console.log(output) // Output #2(1$1
```

## S.No 14 Input = "SIDDUSIDDU" output = "S2I2D4U2"
**Ans:**
```javascript
let input = 'SIDDUSIDDU';
let tmp = {}
for(let ob of input) {
  tmp[ob] = (tmp[ob] || 0) + 1
}
 console.log(tmp) // { S: 2, I: 2, D: 4, U: 2 }

  let result = '';
  for(let obj in tmp) {
    result += obj + tmp[obj]
  }
  return result
}

console.log("Output: ", changeStr(str)) // S2I2D4U2
```

## S.No 15 let nums = [22, 55, 2, 6] sort in ascending order without using inbuilt function in javascript
**Ans:** 
```javascript
let nums = [22, 55, 2, 6];

function bubbleSort(arr) {
    const length = arr.length;
    for (let i = 0; i < length; i++) {
        for (let j = 0; j < length - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                const temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

bubbleSort(nums);
console.log("Sorted array in ascending order:", nums);
```

## S. No 16  Swap two variables without using the 3rd variable
**Ans** Using array destructuring
```javascript
let stringOne = "My home";
let stringTwo = "You home";

[stringOne, stringTwo] = [stringTwo, stringOne];

console.log("String One: ", stringOne);
```

## S.No 17 Take pair of array element list and count their pair occurence
**Ans**
```javascript
let pairElements = [1, 2, 5, 8, 11, 1, 2, 6, 2, 5, 11, 2];

function pairElementsFunction(pairElements) {
  let pairResult = {};
  for (let i = 0; i < pairElements.length - 1; i++) {
      const pair = [pairElements[i], pairElements[i + 1]].toString();
      pairResult[pair] = (pairResult[pair] || 0) + 1;
  }
  return pairResult;
}
console.log("Pair Elements Result: ", pairElementsFunction(pairElements));

// Pair Elements Result:  {
//   '1,2': 2,
//   '2,5': 2,
//   '5,8': 1,
//   '8,11': 1,
//   '11,1': 1,
//   '2,6': 1,
//   '6,2': 1,
//   '5,11': 1,
//   '11,2': 1
// }
```

## S.No 18 Reverse string without using inbuilt function
**Ans:** 
```javascript
let str = "Hello mini";

let revStr = '';

for(let i = str.length - 1; i >= 0; i--) {
  revStr += str[i]
}

console.log("Rev String: ", revStr) // Output: inim olleH
```

## S.No 19: Input - noval(5)(3)() Output - 8. Write a program that can dynamically add numbers using anonymous functions when they are passed as arguments

**Ans:**

```javascript
// Input noval(5)(3)()
function noval(x) {
    return function(y) {
        return function() {
            return x + y;
        }
    }
}
console.log(noval(5)(3)())  // Output 8
 
// Using dynamic method
function x(...args) {
  let sum = args.reduce((total, num) => total + num, 0);
  
  return function(...nextArgs) {
    if (nextArgs.length === 0) {
      return sum;
    } else {
      return x(sum, ...nextArgs);
    }
  };
}

console.log(x(1)(2)(6)()); // Output: 9 REMEMBER: Passing the empty ( ) is Imp!!
```

## S.No 20 Check if the given string is a palindrome
**Ans:**
```javascript
let str = 'ABCBA'
function isPalindrome(str) {
  let originalStr = str.replace(/[^A-Za-z0-9]/g, '')
  let rev = originalStr.split('').reverse().join('');
  if(rev === originalStr) {
    return true
  } else {
    return false
  }
}
console.log("Is pelindrome: ", isPalindrome(str))
// OutPut: True/False
```

## S.No 21 Given two strings check if its Anagram.
**Ans:**
```javascript
let str1 = "Listen Me"
let str2 = "Silent Em"

function isAnagram(str1, str2) {
  let lcStr1 = str1.replace(/\s/g, '').toLowerCase()
  let lcStr2 = str2.replace(/\s/g, '').toLowerCase()
  
  let sortedStr1 = lcStr1.split('').sort().join('')
  let sortedStr2 = lcStr2.split('').sort().join('')
  
  if(sortedStr1 === sortedStr2) {
    return true
  } else {
    return false
  }
  
}

console.log("Is Anagram? ", isAnagram(str1, str2))
```

## S.No 22 Sort the list, remove duplicates both with and without using built-in methods, and find the maximum and second maximum values from the array
**Ans:**
```javascript 
const str = [66, 88, 9, 32, 66, 9, 8]
// Sort using sort()
console.log(str.sort((a,b)=>a-b)) // [8,  9,  9, 32, 66, 66, 88]

// remove dublicate using filter()
console.log(str.filter((a,b)=> str.indexOf(a) === b)) // [ 8, 9, 32, 66, 88 ]

// remove dublicate using Set()
console.log([...new Set(str)]) // [ 8, 9, 32, 66, 88 ]

// remove dublicate without method
let removedDublicate = []
for(let i=0; i< str.length; i++){
  if(removedDublicate.indexOf(str[i]) === -1) {
    removedDublicate.push(str[i])
  }
}
console.log(removedDublicate) // [ 8, 9, 32, 66, 88 ]

// Find the maximum value
const maxValue = Math.max(...str);
console.log('Maximum value:', maxValue); // 88

// Remove the maximum value and find the second highest value
const secondHighestValue = Math.max(...str.filter(item => item !== maxValue));
console.log('Second highest value:', secondHighestValue); // 66

```

## S.No 23 Get only even number from given array
**Ans:**
```javascript
let arr = [20, 15, 64, 26, 3, 7,9]

let empty = []
// using filter method
function even(arr) {
  return arr.filter((num) => num % 2 === 0)
} // Output: [ 20, 64, 26 ]

// Using loop
for(let i=0; i< arr.length; i++) {
  if(arr[i] % 2 === 0) {
    empty.push(arr[i])
  }
}
console.log("Even num array:", empty) // Output: [ 20, 64, 26 ]

```

## S.No 24 Find second largest number in a array
**Ans:**
```javascript
let arr = [10, 5, 8, 3, 1];

let largest = arr[0];
let secondLargest = -Infinity; // Important

for(let i= 1; i< arr.length; i++) {
  if(arr[i] > largest) {
    secondLargest = largest // Important
    largest = arr[i]
  } else if(arr[i] > secondLargest) {
    secondLargest = arr[i]
  }
}

console.log("2nd largest value: ", secondLargest) // Output 8
```

## S.No 25  Find largest value from the nested array
**Ans:**
```javascript 
let nestedArray = [
  [88,8,3], [23, 45, 66], [2,3,8,57]
  ];
largest = nestedArray[0][0]
for(let arr of nestedArray) {
  for(let num of arr) {
    if(num > largest) {
      largest = num
    }
  }
}
console.log("Largest value from nested array: ", largest) // 88
```

## S.No 26 Find dublicates and non dublicate values from the array
**Ans:**
```javascript

let arr = [3,6,9,5,3,6]

let dublicate = []

let nonDublicate = []

for(let i = 0; i<arr.length; i++) {
  if(!nonDublicate.includes(arr[i])) {
    nonDublicate.push(arr[i])
  } else {
    dublicate.push(arr[i])
  }
}

console.log('du:', dublicate, 'non-du:', nonDublicate) // du: [ 3, 6 ] non-du: [ 3, 6, 9, 5 ]
```

## S.No 27 Find factorial of given Number
**Ans:**
```javascript
let n = 5;
let num = 1
// Using iteration - loop
function fact(n) {
  for(let i=1; i<=n; i++) {
    num *= i // same as num = num * i
  }
  return num
} // Output: 120

Eg: 1*2*3*5 = 120

// Using recurtion 
function factorial(n) {
  if(n === 0) {
    return 1
  } else {
    return n * factorial(n-1)
  }
}
console.log(fact(4)) // Output: 120

```

## S.No 28 Check if given number is prime or not
**Ans:** Prime numbers are only divisible by 1 and themselves. A prime number is a positive integer greater than 1 that has exactly two factors, 1 and the number itself. For example, 2, 3, 5, 7, 11, and 13 are prime numbers. 
Note: Prime numbers are essential to secure data encryption and decryption in cryptography

```javascript
let n = 6;
function isPrime(n) {
  for(let i=2; i<n; i++) { // Important i = 2 and i < n
    if(n % i === 0 ) {
      return "no"
    }
  }
  return "yes"
}
console.log(`${n} Is Prime? `, isPrime(n))
```

## S.No 29  Write a program to return fibonacci series
**Ans:**
```javascript 

function fibo(num) { 

  let fibo = []
  
  for(let i= 0; i< num; i++) {
    if(i > 1) {
      fibo.push(fibo[i-1] + fibo[i-2] )
    } else {
      fibo.push(i)
    }
  }
  return fibo
} 
console.log("Fibonacci series: ", fibo(8)) // [0, 1, 1, 2, 3, 5, 8, 13]

// Using recurtion 
function fibonacci(n) {
  if (n <= 1) {
    return n;
  } else {
    return fibonacci(n - 1) + fibonacci(n - 2);
  }
}
for (var i = 0; i < 10; i++) { // Important - has to write for loop
  console.log(fibonacci(i));
}
```

## S.No 30 Write a program to implement quick sort
**Ans:**
```javascript 
function quickSort(arr) {
    if (arr.length <= 1) {
        return arr;
    }

    const pivot = arr[Math.floor(arr.length / 2)];
    const left = [];
    const right = [];

    for (let i = 0; i < arr.length; i++) {
        if (arr[i] < pivot) {
            left.push(arr[i]);
        } else if (arr[i] > pivot) {
            right.push(arr[i]);
        }
    }

    return quickSort(left).concat([pivot], quickSort(right));
}

const arr = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5];
console.log('Original array:', arr);

const sortedArr = quickSort(arr);
console.log('Sorted array:', sortedArr);
```

## S.No 31 Given nested object obj = {'a': {'b': 'Hello', c: {'d': 'World'}}}, find its keys. The output should be array of keys - ['a', 'b', 'c', 'd']
**Ans**

```javascript
function getAllKeys(obj) {
  let keys = [];
  for (let key in obj) {
    keys.push(key);
    if (typeof obj[key] === 'object') {
      keys = keys.concat(getAllKeys(obj[key]));
    }    
  }
  return keys;
}

const obj = {'a': {'b': 'Hello', 'c': {'d': 'World'}}};
const keys = getAllKeys(obj);
console.log(keys); // Output: ['a', 'b', 'c', 'd']
```

## S.No 32 Coping from one object to other object how do you do it, for example const obj = {x:4} so the output should be obb2 = {name:xy, x:4}
**Ans**
- Using spread oporator
```javascript
const obj1 = { x: 4 };
const obj2 = { name: 'xy', ...obj1 };
// Output : {name: 'xy, x: 4}
```

- Using Object.assign() method
```javascript
const obj1 = { x: 4 };
const obj2 = {name: 'xy'}
const result = Object.assign(obj1, obj2)
// Output : {name: 'xy, x: 4}
```

## S.No 33 Reformat given object
**Ans**
```javascript
var x = [{
   name : "Ram",
   age : 25,
   number : 987654321
}]

const output = x.reduce((result, item) => {
  result[item.name] = { age: item.age, number: item.number };
  return result;
}, {});

Output:
{
  "Ram": {
    age : 25,
    number : 987654321
  }
```

## S.No 34 What are different ways to deep copy an array of objects:
**Ans**
- Using spread operator `...`
- Using Json parse : `JSON.parse(JSON.stringify(arr))`


## S.No 35 Give example for Promise solving callback hell
**Ans**
```javascript
async function example() {
  try {
    const result1 = await asyncFunction1();
    const result2 = await asyncFunction2(result1);
    const result3 = await asyncFunction3(result2);
    console.log(result3);
  } catch (error) {
    console.error(error);
  }
}
```

## S.No 36 Write a program to transform an array into an object with 'name' as key using normal and reduce methods:
**Ans**
```javascript
var a = [
  { "name": "abc", "phone": 1234 },
  { "name": "abcd", "phone": 12345 },
  { "name": "abcde", "phone": 123456 }
];

1) Using a for loop:

var outputNormal = {};
for (let item of a) {
  outputNormal[item.name] = { phone: item.phone };
}

2) Using reduce method

var outputReduce = a.reduce((result, item) => {
  result[item.name] = { phone: item.phone };
  return result;
}, {});

```

## S.No 37 Explain below questions
**Ans**
```html
   1. can you iterate an object using for of loop?
      Ans : No
 
   2. Does callback is used to achieve synchronous or asynchronous flow?
      Ans: Asynchronous flow
 
   3. what is the typeof null?
      Ans: Object
 
   4. what is the function of delete operator?
      Ans: Delete operator is used to delete the object property and its value
  
   5. How do you push any elements to beginning of the array?
      Ans: Using unshift method
   
   6. How do you find if an object is empty?
      Ans: using this syntax Object.keys(object).length == 0

```

## S.No 38 List out ES6 features
**Ans**
- let and const
- Arrow Functions
- Template Literals
- Destructuring Assignment
- Default Parameters
- Rest and Spread Operators
- Classes
- Promises
- Modules
- Symbol
- Map and Set
- Iterators and Generators

## S.No 39 Given input let arr = [undefined, 11, 'test', 0, { key: 'test'}, [1, null, 'test', {}], {}, [], null, "", NaN, false, true] from this exclude:  undefined, null, [], {}, NaN
           
**Ans**
```javascript


```

