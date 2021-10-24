# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors belong to the family of regex tokens that don't match any characters, but that assert something about the string or matching process. Anchors assert that the engine's current position in the string matches a well-determined location: for instance, the beginning of the string, or the end of a line.

#### Caret

- ^ - (Caret) asserts the current position in the string as the beginning of the string.

```js
let str = 'Javascript';
consle.log(/^J/.test(str));
```
```js
let str = 'JavaScript';
console.log(/t$/.test(str));
```

- $ - (Dollar) Defines the end of the string.

### Quantifiers

Quantifiers specify how instances of a character, group, or character class has to be present in the input for a match to be found.

#### Exact Count

A number in curly braces {n} is the simplier quanitifer. When you append it to a character or character class, it specifies how many characters or character classes you want to match. 

```js
let str = 'ECMAScript 2021';
let re = /\d{4}/;

let result = str.match(re);

console.log(result);
```
The output would be ["2021"].

#### Range

The range matches a character or character class from n to m times. 

To find numbers that have two, three or four digits, you use the regular expression /\d{2,4}/g:

```js
let str = 'The official name of ES11 is ES2021';
let re = /\d{2,4}/g;

let result = str.match(re);
console.log(result);
```
The output would be ["11", "2021"].

### Grouping Constructs

Grouping Constructs can be used many ways to delineate subexpressions of a regular expression and capture substrings of an input string.

* Match a subexpression that is repeated in the input string.
* Apply a quantifier to a subexpression that has multiple regular expression language elements.
* Include a subexpression in the string that is returned by the Regex.Replace and Match.Result methods.
* Retrieve individual subexpressions from the Match.Groups property and process them separately from the matched text as a whole.

Only parentheses can be used for grouping. Square brackets define a character class, and curly braces are used by a quantifier with specific limits.

### Bracket Expressions

Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

```js
'elephant'.match(/[abcd]/) // -> matches 'a'
```
You will often see ranges of the alphabet or all numerals. [A-Za-z] [0-9] Remember that these character sets are case sensitive, unless you set the i flag.

```js
'elephant'.match(/[a-d]/) // -> matches 'a'
'elephant'.match(/[A-D]/) // -> no match
'elephant'.match(/[A-D]/i) // -> matches 'a'
```

### Character Classes

A character class allows you to match any symbol from a certain character set. A character class is also called a character set. 

The most commonly used character classes are:

- \d – match a digit or a character from 0 to 9.
- \s – match a whitespace symbol such a space, a tab (\t), a newline (\n), etc.
- \w – w stands for word character. It matches the ASCII character [A-Za-z0-9_] including Latin alphabets, digits, and the underscore (_).

```js
let str = 'CO2 is carbon dioxide';
let re = /\w\d/g

console.log(str.match(re));
```
The output would be CO2.

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
