# Regex Gist

Regular Expressions, commonly referred to as RegEx, are sequences of characters that form patterns which can be used to perform searches within text. These regular expressions can range in complexity, sometimes being just one character! Regardless of their length they will always maintain a similar purpose which is to search for a set of strings that matches a specific pattern, this can be extremly powerful when trying to filter data in large documents. The following document will describe a particular RegEx, its use-case, and its functionality.

## Summary

Phone number verification can appear tricky, for a business owner the abilty to store client's contact information can be incredibly vital but when the clients themselves enter their information it can make your database susceptible to bad data. This problem can become more complex when we consider the variation between international phone numbers. Cell phone numbers in the U.S. are a standard 10 digits but can be as high as 13 in Austria, we need to be able to account for different lengths and prefixes for the data that's inserted into our database.

The Regular Expression below has the ability to do this for us and we'll be breaking down exactly how this works.
Review the following snippit:
```
/^\(?(\d{3})\)?[- ]?(\d{3})[- ]?(\d{4})$/
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

Let's start with a quick breakdown of what each component means:

* /^\(? : The number may start with an open parenthesis.
* (\d{3}) : Then three numeric digits must be entered for valid formats. If there is no parenthesis, the number must start with these digits.
* \)? : It allows you to include a close parenthesis.
* [- ]? : The string may optionally contain a hyphen. It can be placed either after the parenthesis or following the first three digits. For example, (123)- or 123-.
* (\d{3}) : Then the number must contain another three digits. For example, it can look like this: (123)-456, 123-456, or 123456.
* [- ]? : It allows you to include an optional hyphen in the end, like this: (123)-456-, -123- or 123456-.
* (\d{4})$/ : Finally, the sequence must end with four digits. For example, (123)-456-7890, 123-456-7890, or 123456-7890.


### Anchors

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
