# Challenge 1 - Square(n) Sum
### Link: https://www.codewars.com/kata/515e271a311df0350d00000f

### Challenge
Complete the square sum function so that it squares each number passed into it and then sums the results together.

For example, for `[1, 2, 2]` it should `return 9` because `1^2 + 2^2 + 2^2 = 9.`

### Solution: 
```JavaScript
function squareSum(numbers){
  let total = 0;
    for (let i of numbers) {
      let squaredNumber = Math.pow(i, 2);
      total += squaredNumber;
    }
  return total;  
}
```

# Challenge 2 - Find GitHub Admins
### Link: https://www.codewars.com/kata/582dace555a1f4d859000058/

### Challenge: 
You will be given an array of objects representing data about developers who have signed up to attend the next coding meetup that you are organising.

Given the following input array:
```JavaScript
var list1 = [
  { firstName: 'Harry', lastName: 'K.', country: 'Brazil', continent: 'Americas', age: 22, language: 'JavaScript', githubAdmin: 'yes' },
  { firstName: 'Kseniya', lastName: 'T.', country: 'Belarus', continent: 'Europe', age: 49, language: 'Ruby', githubAdmin: 'no' },
  { firstName: 'Jing', lastName: 'X.', country: 'China', continent: 'Asia', age: 34, language: 'JavaScript', githubAdmin: 'yes' },
  { firstName: 'Piotr', lastName: 'B.', country: 'Poland', continent: 'Europe', age: 128, language: 'JavaScript', githubAdmin: 'no' }
];
```
Write a function that when executed as findAdmin(list1, 'JavaScript') returns only the JavaScript developers who are GitHub admins:
```JavaScript 
[
  { firstName: 'Harry', lastName: 'K.', country: 'Brazil', continent: 'Americas', age: 22, language: 'JavaScript', githubAdmin: 'yes' },
  { firstName: 'Jing', lastName: 'X.', country: 'China', continent: 'Asia', age: 34, language: 'JavaScript', githubAdmin: 'yes' }
]
```
* The original order should be preserved.
* If there are no GitHub admin developers in a given language then return an empty `array [].`
* The input array will always be valid and formatted as in the example above.
* The strings representing whether someone is a GitHub admin will always be formatted as 'yes' and 'no' (all lower-case).
* The strings representing a given language will always be formatted in the same way (e.g. `'JavaScript'` will always be formatted with upper-case 'J' and 'S'.
### Solution: 
```JavaScript
function findAdmin(list, lang) {
  let adminsArray = [];
 	 for (let i in list) {
    	if (list[i].language === lang && list[i].githubAdmin === 'yes') {
     	 adminsArray.push(list[i]);
    	}
 	 }
  return adminsArray;
}
```

# Challenge 3 - Code Same Language?
### Link: https://www.codewars.com/kata/582dace555a1f4d859000058

### Challenge: 

You will be given an array of objects (associative arrays in PHP, tables in COBOL) representing data about developers who have signed up to attend the next coding meetup that you are organising.

Your task is to return either:

* `true` if all developers in the list code in the same language; or
* `false` otherwise.

For example, given the following input array:
```JavaScript
const list1 = [
  { firstName: 'Daniel', lastName: 'J.', country: 'Aruba', continent: 'Americas', age: 42, language: 'JavaScript' },
  { firstName: 'Kseniya', lastName: 'T.', country: 'Belarus', continent: 'Europe', age: 22, language: 'JavaScript' },
  { firstName: 'Hanna', lastName: 'L.', country: 'Hungary', continent: 'Europe', age: 65, language: 'JavaScript' },
];
```
your function should return `true`.

* The strings representing a given language will always be formatted in the same way (e.g. 'JavaScript' will always be formatted will upper-case 'J' and 'S'
* The input array will always be valid and formatted as in the example above.

### Solution: 
```JavaScript
function isSameLanguage(list) {
  for (let i in list) {
    if (list[i].language !== list[0].language) {
      return false;
    }
  }
  return true;
}
```