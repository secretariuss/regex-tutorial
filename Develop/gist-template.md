# Regex Tutorial

regexs, or regex for short, are a series of special characters that define a search pattern. 
In tutorial, we can see how use regexs to match email

## Summary

In tutorial, we'll see at how the following regex is used to match an email address:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

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
As shown in the highlighted portion of this regex, the components that are highlighted are we call anchors. 
Anchors are used at the start and end of a string or expression. 
In this case ```/^``` and ```$/``` signify the beginning or end of expression.

### Quantifiers
Quantifiers are used to specify how many times a given character is expected to appear.
This regex uses two quantifiers, ```+``` and ```{2,6}```.
In this expression, ```[a-z0-9_.-]+``` means that any character matching the characters inside the brackets is expected to appear  once, with no upper limit.

### Grouping Constructs
Grouping and capturing is done with ```( )``` in regex.
Anything within a set of parentheses is taken as a single group, which allows all the information inside to be treated as a single unit.
Look at the entire expression, paying special attention to the parentheses.

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Between ```/^``` and ```$/```, there are three distinct character groups, ```([a-z0-9_.-]+)```, ```([\da-z.-]+)```, and ```([a-z.]{2,6})```.
In our logic it looks always as simple example ```(emailname)@(website).(domain)```. This is easier to read and understand.

### Bracket Expressions
Bracket expressions are the syntax theory on combining character classes. Multiple character classes may be combined in a single bracket expression.

In this case ```[```a-z0-9```]``` the regex would match any letter or number.

### Character Classes
```\d``` is present in the given matching email code and what it will match a single letter character, a-z, after the @ sign in the email address. 
It means that a letter is matched after the ```@``` in the email and not a number or special character.

### The OR Operator
Character ```|``` as OR operator it is considered an alternation. It matches the expression before or after it. 
This quantifier can affect specific characters, or a whole expression. 
There is none in example.

### Flags
Flags are optional parameters. Each flag is denoted by a single alphabetic character, and serves different purposes in modifying the expression's searching behavior.
There are no flags in our example, however, the following are some examples.

* `m` Multiline flag When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
* `u` Unicode
* `i` Ignores case
* `y` The expression will only match from its lastIndex position and ignores the global (g) flag if set. Because each search in regexs is discrete, this flag has no further impact on the displayed results.
* `s` Dot (.) will match any character, including newline.
* `g` Global search retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.

### Character Escapes
In this matching an email regex:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
We can see that there are 5 separate character escapes.

They are:  ```\.```  ```\d``` ```\.```  ```\.```  ```\.```

The backslash ```( \ )``` in all of the ```( \. )```  is meant to tell the regex to take the (.) literally and search for that as one of the characters in the email addresses. 
It is acknowledging, that email addresses can contain periods (.) in the naming part of the email (for example: alex.secretarius@ukr.net is a valid email that would be picked up by the regex because the period os quite literally there in the name.)

The same goes for where ```( \. )``` is found in the rest of the regex, it can, quite literally, contain a period ```(.)```.

The ```( \d )``` character escape represents any number 0-9

## Author
This tutorial was created by Oleksandr.
GitHub: https://github.com/secretariuss