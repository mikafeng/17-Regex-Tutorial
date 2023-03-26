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
* yukiChan @ gmail . com

To make sure that users input valid email, we will use a regex pattern to compare the user input to.
/[a-z0-9]+@[a-z]+\.[a-z]{2,3}/

Above is a regex literal where the characters are enclosed by // forward slashes. 
In JavaScript, regexs can also be an object called by a constructor function (more on this in a different tutorial).

This regex pattern uses singe characters [a-z][0-9] which are comprised of digits and alphanumeric characters.
The meta character '+' is a quantifier (modifies characters in a previous expression) and means 1 or more. 
In this case it would mean that there needs to be 1 or more characters in the username and domain name to be a valid email address.


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
Exact string matches are case sensitive.

`^`([a-zA-Z0-9._%-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6})*`$`
In the email regex above, the `^` indicates the beginning of the string and `$` indicates the end.
This regex does not search for an exact string match.
It utilizes bracket expressions to search for a range of characters.

### Bracket Expressions

`[]` Bracket expressions enclose a range of characters such as [a-z], [A-Z], [0-9].
These characters are included in the search match.
For example, in our email regex the first set of brackets [a-zA-Z0-9._%-] will match with lowercase and uppercase letters a through z, integers 0 through 9 and the symbols `.`` _`` %` and`-`.

### Quantifiers
`?` `*` `+` Quantifiers let us know how many times we need a character to match. Common quantifiers include:

`+` match 1 or more of the preceding character. 
`?` matches 0 to 1 times; making the match optional.
`*` matches 0 or more times; meaning the character can be absent or repeat any amount of times.
{n} where n is number, can match an exact number of characters needed {3} or a range {3-5}.

In the email regex, we use [a-zA-Z]{2,6}. This indicates that there may be 2 or 3 characters matching a-z such as com or edu.
 
### Character Classes

Character classes are shorthand characters used to match any symbol from a character set.
They are denoted by a `\` . For example, the digit character class is `/d` and will return any match that is a digit.
Common character classes are as follows:

### Flags
Flags are single lowercase characters that changes the default search of the regex.
`i` allows for case-insensitve matching
`g` means global and searches for all occurances
`y` is a sticky flag and starts the search at a given point in the string.

### Grouping and Capturing
Grouping and Capturing use `()` to indicate that the characters between the `()` will be considered a group or set to be matched. Quanitfiers used with `()`, like `()+` will apply to the entire set within.
For example, (nom)+ will match any grouping of nom such as 'nom', 'nomnom', 'nomnomnom' and so on.

## References/Credit
There are many more regex properties and nuances to look up.
This post has referenced [JavaScript Tutorial](https://www.javascripttutorial.net/javascript-regex/) and [The Modern JavaScript Tutorial](https://javascript.info/regular-expressions). 


## Author
Mika is a MERN stack developer, seeking the relationships between coding, art and the environment.
Get a glimpse of their code [here](https://github.com/mikafeng?tab=repositories).
