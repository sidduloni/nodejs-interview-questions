## S.No 1: WAP to print 1-100 without using loop
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

## S.No 2: WAP to display sum of square of an odd nos
**Ans**
```javascript
let a=[1,2,3,4,5,6,7,8,9,10]

const result = a.reduce(1, a) {
  if()
}

function printNumbers(start, end) {
  if (start <= end) {
    console.log(start);
    printNumbers(start + 1, end);
  }
}

printNumbers(1, 20);
```

## S.No 3: Add 2 numbers using recursion 
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

## S.No 4: merge two unsorted arrays into one sorted array with no duplicates
**Ans**
```javascript

let arr1 = [2, 6, 44, 12, 34, 44]
let arr2 = [90, 55, 22, 4, 1, 55, 8]

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

## S.No 5:  Given a string, that contains a special character together with alphabets (‘a’ to ‘z’ and ‘A’ to ‘Z’), reverse the string in a way that special characters are not affected.
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


## S.No 6: Dynamically passing the anonymous functions for sum 
**Ans:**

```javascript
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

## S.No 7: No Write a prototype similar to map in javascript
**Ans:**
```javascript
Array.prototype.mup = function(callback) {
 let emptyArr = [];
 for (let i=0; i < this.length; i++) {
   emptyArr.push(callback(this[i], i, this))
 }
 return emptyArr;
}

let sm = [3, 2]
let ss = sm.mup((num) => num + num) // [ 6, 4 ]
// let ss = sm.mup((num) => num.toString()) // [ '3', '2' ]
// let ss = sm.mup((num, indes) => num + indes) // [ 3, 3 ]
console.log(ss)
```

## S.No 8: Write a async function which should wait until promise resolve
**Ans:**
```javascript
function one() {
  console.log("one");
}

function delay() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log('two');
      resolve('Delay done');
    }, 0);
  });
}

async function two() {
  await delay(); ** Until this promise resolve the one( ) wait then it runs**
  one();
  return 'Function two executed';
}

console.log(3);
two().then((result) => {
  console.log(result);
  
});
console.log(4);
```

## S.No 9: `let nums = [22, 55, 2, 6]` sort in ascending order without using inbuilt function in js
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

## S. No 10 How to handle error without using try-catch
**Ans:**
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

## S. No 11  Swap two variables without using the 3rd variable
**Ans**
```javascript
let stringOne = "My home";
let stringTwo = "You home";

[stringOne, stringTwo] = [stringTwo, stringOne];

console.log("String One: ", stringOne);
```

## S.No 12 Take pair of array element list and count their pair occurence
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
```

## S.No 13 Count consecutive string count in a given string,  Input = 'arrouuppp' output = 'a1r2o1u2p3'
**Ans**
```javascript
let consucativeString = 'arrouuppp';
function consucativeFn(cStr) {
let result = '';
let count = 1;
    for(let i=0; i< cStr.length; i++) {
        if(cStr[i] === cStr[i+1]) {
            count ++
        } else {
            result +=  cStr[i] + count
            count = 1
        }
    }
    return result
}

console.log("consecutive count of String: ", consucativeFn(consucativeString))
```

## S.No 14 Write Callback function and its promise function.
**Ans**
```javascript
function asyncOperation(callback) {
    setTimeout(function() {
        callback("Callback executed");
    }, 3000)
}

function callbackFunc(message) {
    console.log(message)
}
asyncOperation(callbackFunc) // We will not use () here


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

## S.No 15 Write Event emmiter example
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

## S.No 16 WAP to display 1 to 50 without using loop
**Ans**
```javascript
function withoutLoopFn(start, end) {
    if(start <= end) {
        console.log("without using loop: ", start)
        withoutLoopFn(start + 1, end) // Using recurtion
    }
}
withoutLoopFn(1, 5)
```

## S.No 17 WAP to display sum of square of an odd nos in javascript
**Ans**
```javascript
let sumOfSquareArr = [1,2,3,4,5,6,7,8,9,10]
let sumOfSquare = sumOfSquareArr.reduce((acc, cur)=> {
    if(cur % 2 !== 0) {
        return acc + cur ** 2
    }
    return acc
}, 0)

console.log("Square of sum of Odd numbers: ", sumOfSquare)
```

## S.No 17 WAP to convert value to index
**Ans**
```javascript
let vi = {a:2, c:4}
let emptyObj = {}
for(let obj in vi) {
    emptyObj[vi[obj]] = obj
}
console.log('Value to index : ', emptyObj)
```

## S.No 18 Given input -' abbbccddddaab' Print output - 'a1b3c2d4a2b1' consucative 
**Ans**
```javascript
let theInputArr = 'abbbccddddaab';
function consucative(arr) {
    let result = '';
    let count = 1;
    for(let i = 0; i < arr.length; i++) {
        if(arr[i] === arr[i+1]) {
            count ++;
        } else {
            result += arr[i] + count
            count = 1
        }
    }
    return result
}
console.log('consucative : ', consucative(theInputArr))
```

## S.No 19 Create pair of array element and get pair repeated count from array
**Ans**
```javascript
function pcount(arr) {
    let pairRes = {}
    for(let i = 0; i< arr.length - 1; i++ ) {
        const pair = [arr[i], arr[i+1]].toString()
        pairRes[pair] = (pairRes[pair] || 0) + 1
    }
    return pairRes;
}

console.log('Pair count: ', pcount([1, 2, 2, 3, 4, 1, 2, 3, 2, 1]))
```
