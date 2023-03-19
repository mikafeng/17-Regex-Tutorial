# Regex and Email Patterns

A regular expression, often called a regex, is a tool used to search and match patterns in a string.
Regular expressions are made up of meta characters and have several methods that can be leveraged for input validation, algorithms and replacing or matching character patterns. Regular expressions can be used in multiple languages but we will be focusing on Javascript for this tutorial.

## Summary

A common regex is the email pattern. This is often used with email validation and verification input fields.
Let's go over the parts that make up an email regex pattern.

A valid email needs a string before an @ symbol, followed by another string before a . symbol, and finally followed by a string of 2-3 characters.

ex:
* (randomString123) @ (randomString) . (2-3characterString)
* username @ domain_name . domain_end
* github @ github . com
* superHuman @ gmail . com

To make sure that users input valid email, we will use a regex pattern to compare the user input to.
/[a-z0-9]+@[a-z]+\.[a-z]{2,3}/

Above is a regex literal where the characters are enclosed by // forward slashes. 
In JavaScript, regexs can also be an object called by a constructor function (more on this in a different tutorial).

This regex pattern uses singe characters [a-z][0-9] which are comprised of digits and alphanumeric characters.
The meta character '+' is a quantifier (modifies characters in a previous expression) and means 1 or more. 
In this case it would mean that there needs to be 1 or more characters in the username and domain name to be a valid email address.

To gain a better understanding of how regex may be used, consider the code below:

<img width="1026" alt="Screen Shot 2023-03-17 at 5 27 16 PM" src="https://user-images.githubusercontent.com/110942241/226056694-8e6e910e-9149-4e01-9622-1504042cf072.png">


Now, let's get in to the details of the regex components below!


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Boundaries](#boundaries)
- [Back-references](#back-references)


## Regex Components
To create a new Regex object, use the syntax: 
`myregexp = /regex/`

### Anchors
Javascript utilizes the caret `^` and dollar `$` characters.
These characters act as anchors in regex syntax, mathching positional patterns within code.

The `^` anchor matches the beginning of the text.
The `$`anchor matches the end of the text.

The `^` and `$` anchors can match an exact string when text follows it directly.
`/^Reminder/` will match strings that start with 'Reminder'. 
`/end$/` will match strings that end with 'end'.
Exact string mathches are case sensitive.

`^`([a-zA-Z0-9._%-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6})*`$`
In the email regex above, the `^` indicates the beginning of the string and `$` indicates the end.
This regex does not search for an exact string match.
It utilizes bracket expressions to search for a range of characters.

### Bracket Expressions


### Quantifiers
? * +
### Character Classes

### Flags

### Grouping and Capturing


### Boundaries

### Back-references


## Author
Mika is a MERN stack developer, seeking the relationships between coding, art and the environment.
Get a glimpse of their code [here](https://github.com/mikafeng?tab=repositories).
