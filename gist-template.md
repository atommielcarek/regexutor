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

Alternation is the term in Regular Expression that is actually a simple “OR”. The syntax is denoted with a vertical line characer "|". 

Lets say we needed to find programming languages: HTML, PHP, Java or JavaScript. The corresponding RegEx would be: html|css|java(script)

```js
let regexp = /html|php|css|java(script)?/gi;

let str = "First HTML appeared, then CSS, then JavaScript";

alert( str.match(regexp) ); 
```
The output would be 'HTML', 'CSS', 'JavaScript'

### Flags

Flags are optional parameters that we can add to a plain expression to make it search in a different way. Each flag is denoted by a single alphabetic character, and serves different purposes in modifying the expression's searching behaviour.

#### Flags used in RegEx

- i (Ignore Casing) Makes the expression search case-insensitively.
- g (Global) Makes the expression search for all occurences.
- s (Dot All) Makes the wild character . match newlines as well.
- m (Multiline) Makes the boundary characters ^ and $ match the beginning and ending of every single line instead of the beginning and ending of the whole string.
- y (Sticky) Makes the expression start its searching from the index indicated in its lastIndex property.
- u (Unicode) Makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well.

```js
console.log(/foo/ig.flags);
// expected output: "gi"

console.log(/bar/myu.flags);
// expected output: "muy"
```

### Character Escapes

The backslash in a regular expression precedes a literal character. You also escape certain letters that represent common character classes, such as \w for a word character or \s for a space.

```js
Regex(

    "Are you there, Adam?, asked Kevin.", // source

    "(here|there).+(\w+).+(said|asked) (\s) (\w+)\."); // regular expression

    "there, Adam?, asked Kevin."
)
```
* (here|there).+ - Matches “there”, a comma, and a space.
* (\w+) - Matches "Adam".
* .+ - Matches “?, “.
* (said|asked)(\s) - Matches “asked” followed by a space. Without the space, the match would end here; “asked” is followed by a space in the source string.
* (\w+)\. - Matches “Kevin” and a period.


## Author

My name is Adam Mielcarek, I am currently and will forever be learning as much as I can about software engineering and web development and I am always working on new projects and applications. If you have any potential opportunities for collaboration or have any concepts for future projects please feel free to contact me and please take a look at my past projects on GitHub. https://github.com/atommielcarek 
