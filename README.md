# Code-Challenge-Solutions

## Coding Meetup #11 - Higher-Order Functions Series - Find the average age
You will be given a sequence of objects representing data about developers who have signed up to attend the next coding meetup that you are organising.

Given the following input array:
``` js
var list1 = [
  { firstName: 'Maria', lastName: 'Y.', country: 'Cyprus', continent: 'Europe', age: 30, language: 'Java' },
  { firstName: 'Victoria', lastName: 'T.', country: 'Puerto Rico', continent: 'Americas', age: 70, language: 'Python' },
];
```
write a function that returns the average age of developers (rounded to the nearest integer). In the example above your function should return 50 (number).

Notes:

The input array will always be valid and formatted as in the example above.
Age is represented by a number which can be any positive integer.

### Solution
```js
function getAverageAge(list) {
  let totalAge = 0
  for (let i = 0; i < list.length; i++) {
    totalAge = totalAge + list[i].age
  }
  let roundMe = totalAge / list.length
  return Math.round(roundMe)
}
```
## ROT13 Problem
ROT13 is a simple letter substitution cipher that replaces a letter with the letter 13 letters after it in the alphabet. ROT13 is an example of the Caesar cipher.

Create a function that takes a string and returns the string ciphered with Rot13. If there are numbers or special characters included in the string, they should be returned as they are. Only letters from the latin/english alphabet should be shifted, like in the original Rot13 "implementation".

### Solution
```js 
function rot13(message) {
  const lower = 'abcdefghijklmnopqrstuvwxyz'
  const upper = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
  let letterIndex = ''
  let splitMessage = message.split('')
  
  for (let i = 0; i < splitMessage.length; i++) {
    if (splitMessage[i].match(/[a-z]/)) {
      letterIndex = lower.indexOf(splitMessage[i])
      splitMessage[i] = lower[(letterIndex + 13) % lower.length]
    } else if (splitMessage[i].match(/[A-Z]/)) {
      letterIndex = upper.indexOf(splitMessage[i])
      splitMessage[i] = upper[(letterIndex + 13) % upper.length]
    }
  }
  return splitMessage.join('')
  // Find letter in string
  
  // Count 13 letters through string
  
  // Push letter to new array
}
```