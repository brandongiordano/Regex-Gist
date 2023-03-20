# Regex Gist

Regular Expressions, commonly referred to as RegEx, are sequences of characters that form patterns which can be used to perform searches within text. These regular expressions can range in complexity, sometimes being just one character! Regardless of their length they will always maintain a similar purpose which is to search for a set of strings that matches a specific pattern, this can be extremly powerful when trying to filter data in large documents. The following document will describe a particular RegEx, its use-case, and its functionality.

## Summary

Phone number validation can appear tricky, for a business owner the abilty to store client's contact information can be incredibly vital but when the clients themselves enter their information it can make your database susceptible to bad data. Cell phone numbers in the U.S. are standardized at 10 digits but can be written in many different ways, often including paranthesis around the area code or hyphens in between the numbers. We need to be able to account for different formats so that we can store all the data without issue.

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

Let's start with a quick breakdown of what each component of our snippet means:

```
/^\(?(\d{3})\)?[- ]?(\d{3})[- ]?(\d{4})$/
```

* /^\(? : The number may start with an open parenthesis.
* (\d{3}) : Then three numeric digits must be entered for valid formats. If there is no parenthesis, the number must start with these digits.
* \)? : It allows you to include a close parenthesis.
* [- ]? : The string may optionally contain a hyphen. It can be placed either after the parenthesis or following the first three digits. For example, (123)- or 123-.
* (\d{3}) : Then the number must contain another three digits. For example, it can look like this: (123)-456, 123-456, or 123456.
* [- ]? : It allows you to include an optional hyphen in the end, like this: (123)-456-, -123- or 123456-.
* (\d{4})$/ : Finally, the sequence must end with four digits. For example, (123)-456-7890, 123-456-7890, or 123456-7890.


### Anchors
Anchors are regex tokens that don't match any characters but that say or assert something about the string or the matching process. The opening section of our code snippet is a good example. ``` /^\(? ``` indicates that the number may start with an open paranthesis and ``` \)? ``` indicates that our opening 3 numbers may end in a closed parenthesis. We also include ``` [- ]? ``` twice to allow for the inclusion of hyphens between our digits. We also indicate that our phone number must end with 4 digits here ``` (\d{4})$/ ``` the $ indicates the end of the string.

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. The two ``` (\d{3}) ``` sections indicate we want three digits where``` \d ``` lets us to know to look for digits and ``` {3} ``` indicates a quantity of three. This is repeated at the end but instead tells us to look for four ``` (\d{4}) ```.

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
