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

## Shortest Word
Returns the shortest word in a sentence, breaking ties by including the word that appears later in the sentence.

```javascript
function shortestWord(sentence) {
    const words = sentence.split(' ');

    let shortestLength = Infinity;
    let shortestWord = null;
    let shortestIndex = -1;

    words.forEach(function(word, index) {
        const wordLength = word.length;

        if (wordLength < shortestLength || (wordLength === shortestLength && index > shortestIndex)) {
            shortestWord = word;
            shortestLength = wordLength;
            shortestIndex = index;
        }
    });

    return shortestWord;
}
```

## Reverse sentence
Returns a new sentence where the order of the words is reversed.

```javascript
let reverseSentence = function(sentence) {
    // split sentence into words using whitespace as delimiter
    let words = sentence.split(' ');
    // initialise empty array to store reversed words
    let newWords = [];

    // iterate through words array in reverse order
    for (let i = words.length - 1; i >= 0; i--) {
        // add each word to newWords array
        newWords.push(words[i]);
    }

    // join reversed words array into sentence
    let newSentence = newWords.join(' ');
    return newSentence;
}
```

## Contains Word
Accepts two strings as args. Function returns a boolean indicating whether the target word is found inside of the sentence

```javascript
let containsWord = function(sentence, targetWord) {
    let words = sentence.split(' ');

    for (let i = 0; i < words.length; i++) {
        let word - words[i];

        // check if current word matches targetWord
        if (word.toLowerCase() === targetWord.toLowerCase()) {
            return true;
        }
    }
    // if loop completes without finding match
    return false;
}

console.log(containsWord('sounds like a plan', 'like')); // true
```

## Abbreviate Words
Returns a new sentence where words that are longer than 4 characters have their vowels removed.

```javascript
let removeVowels = function(word) {
    let vowels = 'aeiou';
    let newWord = '';

    for (let i = 0; i < word.length; i++) {
        let char = word[i];
        if (!vowels.includes(char)) {
            newWord += char;
        }
    }
    return newWord;
}

let abbreviateWords = function(sentence) {
    let words = sentence.split(' ');
    // initialise empty array to store abbreviated words
    let newWords = [];

    for (let i = 0; i < words.length; i++) {
        let word = words[i];
        if (word.length > 4) {
            // remove vowels
            newWords.push(removeVowels(word));
        } else {
            // if length not greater than 4, keep word unchanged
            newWords.push(word);
        }
    }
    // join abbreviated words array into new sentence using whitespace as delimiter
    return newWords.join(' ');
}

console.log(abbreviateWords('she sends an excellent message ')); // she snds an xcllnt mssg
```

## Snake to Camel
Used to convert a string from snake_case to camelCase.

```javascript
function snakeToCamel(str) {
    // split input string into array of words using underscore character as delimiter
    let words = str.split('_');
    // initialise empty array to store modified words
    let newWords = [];

    for (let i = 0; i < words.length; i++) {
        let word = words[i];
        // capitalise first letter of word and convert rest to lowercase
        let newWord = word[0].toUpperCase() + word.slice(1).toLowerCase();
        // add modified word to newWords array
        newWords.push(newWord);
    }
    // join modified words array into single string without any delimiter
    return newWords.join('');
}

console.log(snakeToCamel('snakes_go_hiss')); // 'SnakesGoHiss'
console.log(snakeToCamel('say_hello_world')); // 'SayHelloWorld'
```
