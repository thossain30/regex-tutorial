# An Introduction to Regex 

In this tutorial, I will go over all the different parts of Regular Expressions, or Regex and what each of them do.

## Summary
A regular Expression, or Regex, is a sequence of characters that define a search pattern for text.
I will be explaining each of the components of the following Regex :

/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

Which is commonly used to verify that user input is a valid email address

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
The anchors are the first and last elements in a regex. The two anchors are ^ and $.
The ^ states that the code/phrase must appear at the beginning of the string i.e. ^The indicates that the string has to begin with "The" to be a match.
The "$" states that the code/phrase must appear at the end of the string i.e. end$ indicates that the string has to end with "end" to be a match.
Since the Regex we are using for this tutorial contains both , the string must match exactly all specifications .
### Quantifiers
We use quantifiers to indicate the number of times a character will appear
This Regex uses 2 quantifiers {2,6} and + . The + is used twice in this expression.
We have [a-z0-9.-] which means that any character within the brackets is expected to appear at least once in our string , without having any limit.
The second use of the + is at [\da-z.-]+ , which also means that any character within the brackets is expected to appear at least once, without any limit.
We also have [a-z.]<u>{2,6}</u> which operates in a different way. The numbers within the curly brackets set the min and max number of times a character from the bracket array can be used. In this case the <b>minimum times a character can match is 2 and the maximum is 6.</b>
### OR Operator
The OR operator is |. It indicates that a match has to contain one phrase or another. For example, in the phrase, a(b|c) a string is a match if it has a followed by b <b>or</b> c (and captures b or c)
Another OR operator is []. For example, a[bc] does the same as the above but does not capture b or c
### Character Classes
The Character classes allow us to write more compact Regular Expressions. In our case, the character class used is \d which is the same as writing 0-9, it means that the character can be any digit between 0 and 9.
\w is another character class which indicates that the character can be any alphanumeric character plus underscore
\s indicates that the character should be a whitespace cahracter i.e. tabs and line breaks
### Flags
Regular expressions have optional flags that allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression.
g is for global search, meaning it'll match all occurrences. i is also a common one which means ignore case.
### Grouping and Capturing
The Grouping and Capturing operator is (). This operator is very useful when we need to extract information from strings or data using your preferred programming language.
For example, with the phrase a(bc), the parentheses create a capturing group with value bc
The Regex used for this tutorial has 3 groups.
The first group is ([a-z0-9_.-]+) , the second group is ([\da-z.-]+) and finally the third group is ([a-z.]{2,6}).
We know that the generic form fo an email address is string@domain.(type of domain like com, edu,org) . That is exactly the 3 point structure of our regex if we use our grouping (group1)@(group2).(group3).
### Bracket Expressions
Bracket Expressions are set by []. Bracket expressions are used to specify one specific character and also set from where that character can be selected.
For example, [abc] matches a string that has either an a or a b or a c. This is the same as saying a|b|c.
In our Regex we have three bracket expressions :
[a-z0-9_.-] In this case the character can be any lowercase letter or a number. It can also contain a hyphen(-), an underscore(_) or a period(.)
### Greedy and Lazy Match
The quantifiers ( * + {}) are greedy operators, so they expand the match as far as they can through the provided text.
For example, <.+> matches <div>simple div</div> in This is a <div> simple div</div> test. In order to catch only the div tag we can use a ? to make it lazy:
### Boundaries
Boundaries are represented by \b and \B. \b represents an anchor like caret (it is similar to $ and ^) matching positions where one side is a word character (like \w) and the other side is not a word character (for instance it may be the beginning of the string or a space character).
### Back-references
Back references are used to match the same text previously matched by a capturing group. This both helps in reusing previous parts of your pattern and in ensuring two pieces of a string match.
In the expression ([abc])\1, using \1 matches the same text that was matched by the first capturing group -
### Look-ahead and Look-behind
Look-ahead and Look-behind allows us to find only matches for a pattern that are followed or preceded by another pattern.
The syntax for lookahead is (?=)
For example, the expression d(?=r) matches a d only if is followed by r, but r will not be part of the overall regex match
In another example, the expression (?<=r)d matches a d only if is preceded by an r, but r will not be part of the overall regex match 
## Author

A software and game developer looking to use his skills to make a positive impact. Check out my Github profile at https://github.com/thossain30
