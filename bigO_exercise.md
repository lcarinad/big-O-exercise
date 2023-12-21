Part 1. 

Simplify the following big O expressions as much as possible:

1. O(n + 10) -> **O(n)**
1. O(100 * n) -> **O(n)**
1. O(25) -> **O(1)**
1. O(n^2 + n^3) -> **O(n)^3**
1. O(n + n + n + n) -> **O(n)**
1. O(1000 * log(n) + n) -> **O(n)**
1. O(1000 * n * log(n) + n) -> **O(n log n)**
1. O(2^n + n^2) -> **O(n)²**
1. O(5 + 3 + 1) -> **O(1)**
1. O(n + n^(1/2) + n^2 + n * log(n)^10) -> ~~O(log n)²~~   ==O(n)^2==

Part 2. 

```
function logUpTo(n) {
	for (let i = 1; i <= n; i++) {
	console.log(i);
		}
	}
```
	
The time complexity for the **logUpTo function** is **O(n)** because the overall work done by the lop grows linearly with the input size.  This function indicates linear growth.

```
function logAtLeast10(n) {
  for (let i = 1; i <= Math.max(n, 10); i++) {
    console.log(i);
  }
}
```
The time complexity for the function **logAtLeast10** is O(n) because the number of operations within the loop will be at the least, 10 and at the most infinity. 

```
function logAtMost10(n) {
  for (let i = 1; i <= Math.min(n, 10); i++) {
    console.log(i);
  }
}
```
The time complexity for the function **logAtMost10** is **O(1)** because the number of operations within the loop will be at the least 1 and at the most 10 so regardless of the input, the amount of operations done by the loop will be no more than 10.

```
function onlyElementsAtEvenIndex(array) {
  let newArray = [];
  for (let i = 0; i < array.length; i++) {
    if (i % 2 === 0) {
      newArray.push(array[i]);
    }
  }
  return newArray;
}
```
The time complexity for the function **onlyElementsAtEvenIndex** is **O(n)**.  The runtime is directly proportional to the input 'n'.

```
function subtotals(array) {
  let subtotalArray = [];
  for (let i = 0; i < array.length; i++) {
    let subtotal = 0;
    for (let j = 0; j <= i; j++) {
      subtotal += array[j];
    }
    subtotalArray.push(subtotal);
  }
  return subtotalArray;
}
```
The time complexity for the function **subtotals** is O(n)^2. The runtime is directly proportional to the input 'n^2' due to the nested loop.  The output increases quadratically.


```
function vowelCount(str) {
  let vowelCount = {};
  const vowels = "aeiouAEIOU";

  for (let char of str) {
    if(vowels.includes(char)) {
      if(char in vowelCount) {
        vowelCount[char] += 1;
      } else {
        vowelCount[char] = 1;
      }
    }
  }

  return vowelCount;
}
```
~~The time complexity for the function **vowelCount** is O(n)^2. The runtime is directly proportional to the input 'n^2' due to the for loop and the nested includes method which is looping through a string.  Because each outer loop triggers an inner loop, the output increases quadratically.~~
==Time Complexity: O(n) // includes is on a fixed length string // the max number of keys is 10==

Part 3.
Answer the following questions

1. True or false: n^2 + n is O(n^2). True
1. True or false: n^2 * n is O(n^3). True
1. True or false: n^2 + n is O(n). False O(n^2)
1. What’s the time complexity of the .indexOf array method? O(n)
1. What’s the time complexity of the .includes array method? O(n)
1. What’s the time complexity of the .forEach array method?O(n)
1. What’s the time complexity of the .sort array method?~~O(n)^2~~ ==O(n log n)==
1. What’s the time complexity of the .unshift array method? ~~O(1)~~ ==O(n)== _?is it O(n) because .unshift returns new length???_ **Response to misconception**: Unshift adds an element(s) to the beginning of an array which requires the operation to move the rest of the array  one(or more) positions to the right. Compared to the push method being O(1) because adding an element to the end of array is an operation that doens't involve shifting existing elements.
1. What’s the time complexity of the .push array method? O(1)
1. What’s the time complexity of the .splice array method? ~~O(1)~~ ==O(n)== _?confused because splice is given an index val and i thought accessing elements in array by index is constant_
1. What’s the time complexity of the .pop array method?O(1)
1. What’s the time complexity of the Object.keys() function?O(n)
BONUS

What’s the space complexity of the Object.keys() function? O(n)
 