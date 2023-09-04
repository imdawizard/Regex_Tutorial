# Understanding the email validation Regex
Introductory paragraph (replace this with your text)

## Summary
Email validation is a comon task in Web Development, and having a solid understanding of how the regex works can be incredibly useful. In this Tutorial we will explore a regular expression(regex) that can be used to validate email addresses. This one: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` including anchors, quantifiires, OR operator, and much more when it comes to emails.

## Table of Contents
- Anchors
- Quantifiers
- OR Operator
- Character Classes
- Flags
- Grouping and Capturing
- Bracket Expressions
- Greedy and Lazy Match
- Boundaries
- Back-references
- Look-ahead and Look-behind

## Regex Components
### Anchors
The anchors are the `^` and the `$`.
You can think of anchors as the beginning and end signs of a road. They tell the regex engine to start looking for a match at the beginning of the text using (`^`) and stop at the end of the text indicated by (`$`). In our case, we're using `^` with bracket notation following (`([a-z0-9_\.-]+)`). Meaning that we're saying "start mathcing now."
### Quantifiers
Quantifiiers define how many times something should occur. `+` means "one or more", so when we see `+` after our first grouping `([a-z0-9_\.-]+)`, it tells the regex to match one or more lowercase letters, digits, underscores, dots or hyphens. This helps us capture the username part of the email. 
### OR Operator
### Character Classes
Character classes (like `[a-z]` `\d`, as used in our code), help us to specify sets of characters we want to match. For example `[a-z]` matches any lowercase letter, and `\d` matches any digit. We use them to ensure that the email address follows the right patterns.
### Flags
We don't use flags in our example email regex. However one common flag that could be used when it comes to emails is `i`. This flag modifies the search to become a case-insensitive search. Which can be useful when talking about emails.
### Grouping and Capturing
As introduced in [quantifiers], groupings are created using `()`. These groups are often referred to as subexpressions. In our example the first part of the email before the `@` symbol(username) is one subexpression of our email we'll break down. In total there are three subexpressions in our example:
1. `([a-z0-9_\.-]+)`
2. `([\da-z\.-]+)`
3. `([a-z\.]{2,6})`

These are cool
### Bracket Expressions
Square brackets `[]` define character sets. For example `[a-z\.]` matches lowercase letters and dots. We use this to check parts of the email address.
### Greedy and Lazy Match
Quantifiers (`+`) are greedy by default, meaingn they try to match as much as possible. Adding `?` after a quantifier (like `+?`) makes it lazy, so it matches as little as possible. We use this for efficient matching.
### Boundaries
### Back-references
### Look-ahead and Look-behind

## Author
A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
