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

# Challenge 8 - Vowel Count
### Link https://www.codewars.com/kata/54ff3102c1bad923760001f3/

### Challenge: 
Return the number `(count)` of vowels in the given string.

We will consider `a, e, i, o, u` as vowels for this Kata (but not y).

The input string will only consist of lower case letters and/or spaces.

### Solution: 
```JavaScript
function getCount(str) {
   let vowelCount = 0;

   const vowelsArray = ['a', 'e', 'i', 'o', 'u'];
   const strArray = str.split('');

   strArray.forEach((el => {
      for (let i in vowelsArray) {
         if (el === vowelsArray[i]) {
            vowelCount++;
         }
      }
   }));
   return vowelCount;
}
```

# Challenge 9 - Count The Monkeys
### Link https://www.codewars.com/kata/56f69d9f9400f508fb000ba7

### Challenge: 
You take your son to the forest to see the monkeys. You know that there are a certain number there (n), but your son is too young to just appreciate the full number, he has to start counting them from 1.

As a good parent, you will sit and count with him. Given the number (n), populate an array with all numbers up to and including that number, but excluding zero.

For example(Input --> Output):
```JavaScript
10 --> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
 1 --> [1]`
 ```
 
 ### Solution: 
 ```JavaScript
function monkeyCount(n) {
  const numbersArray = [];
  
  for (let i = 1; i <= n; i++) {
    if (n <= n) {
      numbersArray.push(i);
    }
  }
  
  return numbersArray;
}
```
# Challenge 10 - Remove Space Strings
### Link https://www.codewars.com/kata/57eae20f5500ad98e50002c5

### Challenge: 
Simple, remove the spaces from the string, then return the resultant string.

### Solution: 
```JavaScript
function noSpace(x){
  return x.split(" ").join('');
}
```

# Challenge 11 - Jenny's Secret Message
### Link https://www.codewars.com/kata/55225023e1be1ec8bc000390

### Challenge: 
Jenny has written a function that returns a greeting for a user. However, she's in love with Johnny, and would like to greet him slightly different. She added a special case to her function, but she made a mistake.

Can you help her?

### Original Input: 
```JavaScript
function greet(name){
  return "Hello, " + name + "!";
  if(name === "Johnny")
    return "Hello, my love!";
}
```

### Solution: 
```JavaScript
function greet(name){
  
  if(name === "Johnny") {
    return "Hello, my love!";
  }
  
  return "Hello, " + name + "!";
}
```

# Challenge 12 - Convert Boolean Strings to Yes/No
### Link: https://www.codewars.com/kata/53369039d7ab3ac506000467

### Challenge: 
Complete the method that takes a boolean value and return a `"Yes"` string for true, or a `"No"` string for false.

### Solution: 
```JavaScript
function boolToWord( bool ){
  if (bool === true) {
    return "Yes";
  } else {
    return "No";
  }
}
```

# Challenge 13 - Opposite number
### Link https://www.codewars.com/kata/56dec885c54a926dcd001095

### Challenge: 
Very simple, given an integer or a floating-point number, find its opposite.

Examples:
```JavaScript
1: -1
14: -14
-34: 34
```
### Solution: 
```JavaScript
function opposite(number) {
  if (Math.sign(number) === 1 ) {
      return -Math.abs(number);
    } 
  return Math.abs(number);
}
```
Reference:
* https://tinyurl.com/positiveToNegativeJS
* https://tinyurl.com/mathSignJS

### Notes:
I've hardly touched Math methods since I've mostly been using string/array methods and so this challenge has showed me the `Math.sign()` method which depending on the parameter taken will return `1 - positive number`, `-1 - negative number`, `0 - positive zero`, `-0 negative zero`, and `NaN` if none of the cases match.

So if the parameter that's being taken in `number` is a positive value then it will call the `-Math.abs()` method that returns the absolute value, and by default this returns a positive integer and so by adding a `-` hyphen, it inverses the operations and returns a negative value when a positive parameter is taken.

# Challenge 14 - Even Or Odd
### Link https://www.codewars.com/kata/53da3dbb4a5168369a0000fe

### Challenge: 
Create a function that takes an integer as an argument and returns `"Even"` for even numbers or `"Odd"` for odd numbers.

### Solution: 
```JavaScript
function even_or_odd(number) {
  if (number % 2 === 0) {
    return 'Even'
  } else {
    return 'Odd';
  }
}
```

  # Challenge 15 - Unfinished Loop - Bug Fixing 
### Link https://www.codewars.com/kata/55c28f7304e3eaebef0000da

### Challenge: 

Oh no, Timmy's created an infinite loop! Help Timmy find and fix the bug in his unfinished for loop!

### Solution: 
```JavaScript
function createArray(number){
  const newArray = [];
  
  for(let counter = 1; counter <= number; counter++){
    newArray.push(counter);
  }
  
  return newArray;
}
```
