# REGEX 

(Regular expressions) are utilized to find certain patterns of characters within a string. They are used to authenticicate input, change a character. This is a regex for matching character information for valid e-mail address.

## Summary

Code snippet that we will be working with for this assignment:

## `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

above code is a line of REGEX that will validate that a email address is an input. This is the code that will be used for this and how this line of code works.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Anchors are used to indentify position of characters, rather then indentify a specific character.

## `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Anchors used in this regular expression are `^` at the beggining and `$` at the end. These contain the expression within them and are 
often used in regular expressions. `$` is used here to end the line but can change depending on which engine is used or if we have multiline. 
 
### Quantifiers

A quantifier is an operator that repeats. Quantifiers will tell the system to match a preceding token a set number of times. They are considered lazy or greedy.

## `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The `+` quantifier is used to communicate another sequence to matched as a greedy quantifier, its going to attempt a match `[a-z0-9_\.-`. The quatifiers for this code is `+` and `{2, 6}`. `{2, 6}` will match two to six from the previous token and in our case it will match `[a-z\.]`.Example `{2}` would match exactly two, and `{2,}` would match two or more.

### OR Operator

The pipe `|` is considered an alternation. It will match expressions that come before and after it in the code but this is not present in our code.

### Character Classes

The character classes match one out of several characters. The order of the characters within the character class do not matter. 

## `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

A character set `[ABC]` will match any single character in the set. In this example `[a-z0-9_\.-]` will match any character within square brackets, a range `[A-Z]` will match a character included between two characters that have been seperated by a hyphen. In this example a-z will match any character between a-z. `0-9` will match any character between zero and nine. 

There are several other character classes that we do not use in this example: 
* A negated set contains a caret first thing within the square brackets `[^ABC]` and matches any character that is not in the set.
* A `.` will match any character except line breaks. The `.` in our example actually refer to actually periods, and are not a character   class.
* Match any `[/s/S]` will match any character.
* Word `/w` will match any word.
* Not word `/W` will match any character that is not a word.
* Digit `/d` matches any number.
* Not digit `/D` will match any character that is not a number.
* Whitespace `\s` will match any character that leaves whitespace (spaces, tabs, line breaks, etc.).
* Not whitespace `\S` will match any character that is not a whitespace character. 

### Flags

No flag was used in this example. Flags follow up the closing forward slash of an expression changing how it is interpreted.

Some examples would be: 
 * Ignore case `i` will make the entire expression case-sensitive.
 * Global search `g` store the index of the last match. 
 * Sticky `y` only matches the last iundex position and ignores global search flag.
 * Unicode `u` allows extended unicode escapes in the form.


### Grouping and Capturing

A Group will allow groups of tokens to be combined. They are then operated on together. 

## `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Capturing group `(ABC)` will make a group of multiple tokens that will be extracted as a substring. This code has three different capturing groups: `([a-z0-9_\.-]+)`, `([\da-z\.-]+)`, `([a-z\.]{2,6})`. The substring will be verified before the `@`, another before the `\`, and the last for the domain name that pertains to the email address.

### Bracket Expressions

Bracket expressions for this code:

## `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

For this email validation it includes:
`[a-z0-9_\.-]`, this is matching any letter a-z (case sensitive) 0-9, "_", "-", and ".' characters.
`[/da-z\.-]` matches a single didgit from 0-9, any character a-z (also case sensitive), and the "." and "-" characters.
`[a-z\.]` matches any characters a-z (alse case sensitive) and "." character.

### Greedy and Lazy Match

This was referenced earlier in the section about quantifiers, mentioned was the terms lazy and greedy. A greedy quantifier will attempt to match as many characters as possible as it reads the string of the regex backwards. 
The lazy quantifier will try to match as few characters as it possibly can as it goes back through the regex string. The default used is greedy unless another quantifier affects the regex.

### Boundaries

boundry is used in a regex by using `\b` this porompts for a check by the engine, it checks that the position in the string is a word boundary. 

This can be at the start of the string, if the first string character is a word character `\w`
Between two characters in the string, where one is a word character `\w` and the other is not.
At string end, if the last string character is a word character `\w`.
