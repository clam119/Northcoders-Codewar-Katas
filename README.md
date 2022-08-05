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

# Challenge 4 - Sentence Smash
### Link: https://www.codewars.com/kata/53dc23c68a0c93699800041d/

### Challenge: 
Write a function that takes an array of words and smashes them together into a sentence and returns the sentence. You can ignore any need to sanitize words or add punctuation, but you should add spaces between each word. **Be careful, there shouldn't be a space at the beginning or the end of the sentence!**

For example, given the following input array:
```JavaScript
['hello', 'world', 'this', 'is', 'great']  =>  'hello world this is great'
```

### Solution:
```JavaScript
function smash (words) {
   return words.join(" ");
};
```

### Notes:
References:
* https://tinyurl.com/jsArrayToStringRef
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join

I broke this CodeWars Kata into manageable steps by first figuring out that you can convert an `Array` into a `String` using `toString();` and looked up how to replace the commas separating the words with a space, and finally returned this to the user.

Update: Refactored and removed `.toString();` because the `.join()` array method by default returns a string, and so there's no need to modify the data type that's being returned. 

# Challenge 5 - Find the 1st Python Developer
### Link: https://www.codewars.com/kata/5827bc50f524dd029d0005f2

### Challenge: 
You will be given an array of objects (associative arrays in PHP) representing data about developers who have signed up to attend the next coding meetup that you are organising. The list is ordered according to who signed up first.

Your task is to return one of the following strings:
* `< firstName here >, < country here >` of the first Python developer who has signed up; or
* `There will be no Python developers` if no Python developer has signed up.

For example, given the following input array:
```JavaScript
const list1 = [
  { firstName: 'Mark', lastName: 'G.', country: 'Scotland', continent: 'Europe', age: 22, language: 'JavaScript' },
  { firstName: 'Victoria', lastName: 'T.', country: 'Puerto Rico', continent: 'Americas', age: 30, language: 'Python' },
  { firstName: 'Emma', lastName: 'B.', country: 'Norway', continent: 'Europe', age: 19, language: 'Clojure' }
];
```
your function should return Victoria, Puerto Rico.
### Solution: 
```JavaScript
function getFirstPython(list) {
  for (let i in list) {
    if (list[i].language === 'Python') {
      return list[i].firstName + ", " + list[i].country
    } 
  }
   return 'There will be no Python developers'
}
```

# Challenge 6 - Is Ruby Coming?
### Link: https://www.codewars.com/kata/5827acd5f524dd029d0005a4/

### Challenge: 
You will be given an array of objects (associative arrays in PHP) representing data about developers who have signed up to attend the next coding meetup that you are organising.

Your task is to return:
* `true` if at least one Ruby developer has signed up; or
* `false` if there will be no Ruby developers.

For example, given the following input array:
```JavaScript
const list1 = [
  { firstName: 'Emma', lastName: 'Z.', country: 'Netherlands', continent: 'Europe', age: 29, language: 'Ruby' },
  { firstName: 'Piotr', lastName: 'B.', country: 'Poland', continent: 'Europe', age: 128, language: 'Javascript' },
  { firstName: 'Jayden', lastName: 'P.', country: 'Jamaica', continent: 'Americas', age: 42, language: 'JavaScript' }
];
```
your function should return true.

### Solution: 
```JavaScript
function isRubyComing(list) {
  for (let i in list) {
    if (list[i].language === 'Ruby') {
      return true
    }
  }
  return false;
}
```

# Challenge 7 - Get the mean of an array
### Link https://www.codewars.com/kata/563e320cee5dddcf77000158/

### Challenge: 
It's the academic year's end, fateful moment of your school report. The averages must be calculated. All the students come to you and entreat you to calculate their average for them. Easy ! You just need to write a script.

Return the average of the given array rounded down to its nearest integer.

The array will never be empty.

### Solution: 
```JavaScript
function getAverage(marks){
  let total = 0;
    for (let i in marks) {
        total += marks[i];
     }
  return Math.floor(total/marks.length);
} 
```

Reference: https://www.delftstack.com/howto/javascript/javascript-sum-of-array/
