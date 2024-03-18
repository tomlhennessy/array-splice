# Array Splice Method

* mutates the original array it's called on
* used for both removing and inserting elements
* Removal: 'splice(targetIndex, numToRemove)'
  - removes 'numToRemove' elements starting from 'targetIndex'
  - returns an array containing the removed elements
* Insertion: 'splice(targetIndex, numToRemove, ...elementsToInsert)'
  - inserts 'elementsToInsert' at 'targetIndex'
  - does not remove any elements ('numToRemove is 0)
* verstile: can remove, insert, or do both simultaeneously


# String.split

* converts string into an array
* syntax: 'string.split(seperator)'
* returns an array where elements are substrings seperated by 'seperator'
* original string is not mutated; a new array is returned
* seperator is removed from resulting array


# Array.join

* syntax: 'array.join(separator)'
* returns a string with array elements concatenated with 'seperator' between each
* original array is not mutated; a new string is returned

## Combining methods
* 'split' turns string into array, 'join' turns array into string
* example: 'str.split('I').join('we')' replaces all "I"s with "we"s
* neither method mutates input; they return new array/string

# Functions

## Initials
Function takes a full name and returns the initials for that name.

```javascript
let intitials = function(name) {
    // split input name into array, seperated by spaces
    let parts = name.split(' ');

    // initialise empty array to store initials
    let firstLetters = [];

    // iterate through each part of name
    for (let i = 0; i < parts.length; i++) {
        // get current part
        let part = parts[i];
        // get first letter of current part and convert to uppercase
        let firstLetter = part[0].toUpperCase();
        // add initial to array
        firstLetters.push(firstLetter);
    }

    // join initials into single string and return
    return firstLetters.join('');
}

console.log(initials('anna paschall')); // 'AP'
```

## Longest Word
Finds and returns the longest word in a sentence.

```javascript
let longestWord = function(sentence) {
    // split the input sentence into array of words
    let words = sentence.split(' ');

    // intialise variable to store longest word so far
    let longestWord = '';

    // iterate through each word
    for (let i = 0; i < words.length; i++) {
        // get current word
        let word = words[i];

        // check if length of current word is greater than longestWord
        if (word.length > longestWord.length) {
            // if true, update longestWord to current word
            longestWord = word;
        }
    }

    return longestWord;
}

console.log(longestWord('where did everyone go')); // 'everyone'
```
