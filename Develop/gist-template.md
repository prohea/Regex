# Regex Tutorial

Tutorial explaining regex

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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
To match a position instead of any character. Most commonly used anchors are \b^ and $. 
^ matches the start of a string while $ matches the end of a string. If you have multiple lines then you can opt for multiline mode i.e m after the second forward slash. /regex/m

Examples:
/^regex$/mg
/^\d{4}$/mg

### Quantifiers
Used for repetition. 
If you want to match flavor and flavour you may use: /flavou?r

? as a metacharacter here means zero or one repetition. Simply, it looks to see if that particular character is present or not. Making the character optional. The regex will select if the character is there, and it will also match if the character is not in the test string.

For zero or more repetition * is used. This specific metacharacter will match in case a character has no existence to any number of occurrence.

.* will select any number of characters.

For one or more repetition + is used. + metacharacter will match only if the character or group before + occurs at least once. However, it will match any additional occurrences.

\d+ will match one digit up to any digit number. 
\d is the shorthand character class for 0-9 and + means one or more repetition. 
\d+ will match all numbers in the string.

Another form of repetition is to use braces. There are three instances:
1. {fixed}
Fixed number of repetition. Within the braces, type the total number of repetitions required to match using digits. As an example, if you wanted to match all four digit numbers simply type: /\d{4}
This regex will match 1234, 4567, 2589, 5478. It will not match 12, 258, 357, 8, and so on.

2. {min, max}
Match numbers with a minimum of two digits and a maximum of five digits. Example: /\d{2.5}\
The regex will match all numbers which are two digits, three digits, four digits and five digits. It will not match one digit or six digit numbers.

3. {min}
When you have a minimum number of digits required in a number but don't have the information about the maximum number of digits. 

### OR Operator

### Character Classes
A character class or character set may direct regex to match only one character out of two or more. The syntax of a character class is to put two or more characters inside square brackets: [class]

You can put any number of characters in a character class. However, your regex engine is going to match only one out of a given set of characters.
Like you want to match affect and effect: /[ae]ffect/g
Regex will match both affect and effect.

Words with two different acceptable spellings can also be matched.
If you want to match gray or grey: /gr[ae]y/g

Some words can be misspelled for example the word separate has four possible forms: separate, seperate, separete, seperate
To match any variant of separate the regex should be: /sep[ae]r[ae]te/g

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
