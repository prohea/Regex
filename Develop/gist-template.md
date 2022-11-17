# Regex Tutorial

Tutorial explaining regex.

## Summary

A __*Regular Expression*__ (__regex__) is a syntax that allows you to match strings with specific patterns. It is a suped-up text search shortcut, but a regular expression __adds the ability to use quantifier, pattern collections, special characters, and capture groups to create extremely advanced search patterns.__ 

Regex can be used any time you __*need to query string-based data*__, such as:
- *Analyzing command line output*
- *Parsing user input*
- *Examining server or program logs*
- *Handling text files with a consistent syntax, like a CSV*
- *Reading configuration files*
- *Searching and refactoring code*

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

# Anchors
To match a position instead of any character. Most commonly used anchors are \b^ and $. 
^ matches the start of a string while $ matches the end of a string. If you have multiple lines then you can opt for multiline mode i.e m after the second forward slash. /regex/m

Examples:
/^regex$/mg
/^\d{4}$/mg

# Quantifiers
__*Check to see how many times you should search for a character.*__
*List of all quantifiers:*
 ```a|b``` Match either __a__ or __b__ .
```?``` __Zero__ or __one__.
```+``` __One__ or __more__.
```*``` __Zero__ or __more__.
```{N}``` __*Exactly*__ __N__ number of times (*where N is a number*).
```{N,}``` __N__ or __more__ number of times (*where N is a number*).
```{N,M}``` __*Between*__ __N__ and __M__ number of times (*where N and M are number and* **N < M**).
```*?``` __Zero__ or __more__, but __*stop*__ __after first match__.
# OR Operator

# Character Classes
A character class or character set may direct regex to match only one character out of two or more. The syntax of a character class is to put two or more characters inside square brackets: [class]

You can put any number of characters in a character class. However, your regex engine is going to match only one out of a given set of characters.
Like you want to match affect and effect: /[ae]ffect/g
Regex will match both affect and effect.

Words with two different acceptable spellings can also be matched.
If you want to match gray or grey: /gr[ae]y/g

Some words can be misspelled for example the word separate has four possible forms: separate, seperate, separete, seperate
To match any variant of separate the regex should be: /sep[ae]r[ae]te/g

# Flags
An option parameter to a regex that modifies its behavior of searching.
```i``` ignore/casing; makes the expression search case-insensitively.
```g``` global; makes the expression search for all occurrences.
```s``` dot all; makes the wild character . match newlines as well.
```m``` multiline; makes the boundary characters ^ and $ match the beginning and ending of every single line instead of the beginning and ending of the whole string.
```y``` sticky; makes the expression start its searching from the index indicated in its lastIndex property.
```u``` unicode; makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well.

# Grouping and Capturing
Groups allow you to search for more than one item at a time. Example:
/(Testing|tests) 123/ig

Groups are defined by parenthesis. There are two different types of groups; Capture Groups and Non-Capturing Groups:
(...) Group matching any three characters
(?:...) Non-capturing group matching any three characters
The difference between the two comes up in the conversation when "replace" is part of the equation. 

Can also match more than a single group, like both (Testing|tests) and (123)

# Bracket Expressions
Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

# Greedy and Lazy Match
```+``` Matches __one__ or __more__ characters. This *quantifier* is considered __*greedy*__ by default. Example:
```Hi+```
However, if you change it to be __*lazy*__ using a question mark symbol (__?__), the behavior changes. Example: 
```Hi+?```
Now, the __*i*__ matcher will try to match as __few__ times as possible. Since the __+__ icon means *one or more*, it will only match *one* __i__. This means that if we input the string *Hiiii*, only *Hi* will be matched. 
While this isn't particularly useful on its own, when combined with with broader matches like the __.__ symbol, it becomes extremely important. 
```.``` used to find __any character__. Example:
```H.*llo``` can match everything from *Hillo* to *Hello* to *Hellollollo*.
```H.*?llo``` __only__ matches *Hello*.

## Pattern Collections
Here's a list of the *most common pattern collections*:
```[A-Z]``` Match __any uppercase character from__ __*A*__ to __*Z*__.
```[a-z]``` Match __any lowercase character from__ __*a*__ to __*z*__.
```[0-9]``` Match __*any number*__.
```[asdf]``` Match __any character that's either__ __*a*__, __*s*__, __*d*__, or __*f*__.
You can even combine these together:
```[0-9A-Z]``` __Match any character that's either a number or a capital letter from__ __*A*__ to __*Z*__.
```[^a-z]``` __Match any__ __*non-lowercase*__ __letter__.

# Boundaries
Boundary markers allow yo to anchor the regex pattern to the beginning and end of the line (or string depending on which flags you use). This means that when you want to match a literal you need to escape these special characters with a backslash. 

# Back-references
Match the same text as previously matched by a capuring group. 

# Look-ahead and Look-behind
Extremely powerful. There are four types of lookahead and behinds:
(?!) negative lookahead.
(?=) positive lookahead.
(?<=) positive lookbehind.
(?<!) negative lookbehind.

Lookahead looks like it sounds like: it either looks to see something is after the lookahead group or is not after the lookahead group, depending on the positive or negative.

## Author
Hope is a coder who enjoys learning new things. Github: (https://github.com/prohea)
