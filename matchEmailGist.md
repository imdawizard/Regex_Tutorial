# Understanding the email validation Regex
Introductory paragraph (replace this with your text)

## Summary
Email validation is a comon task in Web Development, and having a solid understanding of how the regex works can be incredibly useful. In this Tutorial we will explore a regular expression(regex) that can be used to validate email addresses. This one: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` including anchors, quantifiires, OR operator, and much more when it comes to emails.

## Table of Contents
- [Anchors](###Anchors)
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
- [Author](#Author)

## Regex Components

### Anchors

The anchors are the `^` and the `$`.
You can think of anchors as the beginning and end signs of a road. They tell the regex engine to start looking for a match at the beginning of the text using (`^`) and stop at the end of the text indicated by (`$`). In our case, we're using `^` with bracket notation following (`([a-z0-9_\.-]+)`). Meaning that we're saying "start mathcing now."

### Grouping and Capturing

Goupings are created using `()`. These groups are often referred to as subexpressions. In our example the first part of the email before the `@` symbol(username) is one subexpression of our email we'll break down. In total there are `3` subexpressions in our example:
1. `([a-z0-9_\.-]+)`
2. `([\da-z\.-]+)`
3. `([a-z\.]{2,6})`

In between each grouping we have what are called literal characters which must be matched exactly as they are written. In our example we have the `@` symbol and the `\.`, right now we can ignore the backslash in front of the `.`(read more in ### character escapes). But this checks out because emails have two very specific characters. For example in this email "test@gmail.com", we can have whatever username, followed by the `@` symbol, followed by the website name, a '`.`' then the type of website(ex. .com, .edu, .fi). Now that we have our subexpressions let's abstract even further into our expression by looking at each character in our subexpressions.

### Character Classes

Character classes (like `[a-z]` `\d`, as used in our code), help us to specify sets of characters we want to match. For example `[a-z]` matches any lowercase letter, and `\d` matches any digit. We use them to ensure that the email address follows the right patterns. So let's break down all the character classes in each of our subexpressions.
1. `([a-z0-9_\.-]+)`
In this expression we have the following character classes:
    - `a-z`  --This is a range of characters spaning from a-z, lowercase only
    - `0-9`  --This is a range of numbers spaning from 0-9
    - `_`  --This is the literal '`_`' underscore symbol.
    - `\.`  --You can ignore the `\` for now, we'll go over this more in character escapes, but this just includes the '`.`'

Summary:
    This first subexpression basically looks for any combination of any lowercase letter, any number, the `-`, and the `.`, it is quite robust in it's search criteria. 

2. `([\da-z\.-]+)`
    New charcter classes in this subexpression:
    - `\d`  --You can imagine this as the same as 0-9, it acheives the same match

Summary:
    This middle subexpression looks for any combination of any lowercase letter, any number, a period, and the hypen characters.

3. `([a-z\.]{2,6})`
    This subexpression uses character classes we've already learned!

Summary:
    This last subexpression looks for any combination of any lowercase letter and the period!

So if we combine these expressions we get (any letter + any numbers + _ + . + -)@(any number + any letter + . + -).(any letter + .). We'll go over the numbers at the end later, but that's basically the gist!

### Character Escapes

Remember when I kept telling you ignore the backslashes? Well now I will finally explain them. The backslashes are used when you want to include that literal special character that could be misinterpreted to mean something else by the regex engine. In our example we want to include the period, but if we insert the period by itself the engine will get confused! This is beause the `.` will cause the engine to match any character except the newline character. So we add the `\` in order to let the expression know we what the character '`.`'.

### Quantifiers
Quantifiiers define how many times something should occur. The `+` means "one or more", so when we see `+` after our first grouping `([a-z0-9_\.-]+)`, it tells the regex to match one or more lowercase letters, digits, underscores, dots or hyphens. This helps us capture the username part of the email. 

Another quantifier in our example is the last letters in the brackets: '`{2, 6}`'. In this qunatifer we will use this formula: {n, x} where the pattern is matched from the proceding token from a minimun of n number of times to a maxiumum of x number of times. So in our example the last subexpression will be matched a minimun of 2 times and a maximum of 6 times.

### Flags
We don't use flags in our example email regex. However one common flag that could be used when it comes to emails is `i`. This flag modifies the search to become a case-insensitive search. Which can be useful when matching emails.

### Bracket Expressions

Square brackets `[]` define character sets. For example `[a-z\.]` matches lowercase letters and dots. We use this to check parts of the email address. You'll notice that 

### Greedy and Lazy Match
Quantifiers (`+`) are greedy by default, meaingn they try to match as much as possible. Adding `?` after a quantifier (like `+?`) makes it lazy, so it matches as little as possible. We use this for efficient matching.

## Author
<a name="Author"></a>
Nate Kester

Nate Kester lives in Utah and is a student of the EdX full stack web Development bootcamp working on thereafter getting a job in Web Deveopment. The following is link to the author's GitHub:
[nate's GitHub repo](https://github.com/imdawizard )
