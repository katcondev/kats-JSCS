# Kat's Regex Tuts

Regular expressions, also referred to as "regex" or "regexp" are patterns used to match strings. A regex can be a potent and valuable tool if used correctly. The following is a regex tutorial on matching an email,  a commonly needed feature in web development. 

## Summary

Below is a regex used to match an email. In this tutorial, I'll describe all the components that are part of the regex used to validate an email address. 

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

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

Anchors denote where the expression starts and ends. We use the '^' (carat) to start an expression, and '$' (dollar) to end it. The following example expression matches the following email pattern 'kat@gmail.com' 

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

### Quantifiers

Quantifiers match a number of instances of a character, group, or character class in a string.  In this instance, our regex uses quantifiers three times; those quantifiers are the '+' and '{2,6}', within the parenthesis '()' also known as the capture group.  

- The first set of quantifiers, shown below in sections for clarity, is using '+'.  This regex is telling us to match a character between one and unlimited times, as many as possible.  There is no set character length limit. 
Match lowercase character range and a digit character range and also include '_', '.' and '-' literally.  Also '0-9' and '\d' are referring to digit characters. 

    ```
    [a-z0-9_\.-]+ 
    
    [\da-z\.-]+
    ```

- The second set, or third quantifier is '{2,6}' Match everything with a character between two and six times, as many as possible. This gives a set range. 

    ```
    [a-z\.]{2,6}
    ```

### OR Operator
The OR operator is denoted using '|' or pipe.  It is used to match expressions to the left or right of the '|' operator.  There are no OR operators in this regex. A quick example not part of our regex, 'this' or 'that'

```
this | that
```


### Character Classes
Character classes denote different types of characters. In our example we are specifying the use of lower case characters, digits and some special type characters. 

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
- Character Range
    - 'a-z' lowercase characters
    - '0-9' and '/d' digits
    - '_' '-' literal characters
    - '.' and '@' literal and exact locations 


### Flags
Flags are a fundamental part of the regex, this particular regex does not contain flags.  Flags are found after the second set of '/' or the end of a regex. A quick flag used in our regex to make it case insensitive would look like:

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/i
```


### Grouping and Capturing
Parenthesis '()' are used to denote capture groups. In our regex we have three capture groups seperated by literal characters '@' and '.'  You can add '?:' to disable the capturing group or use '?<name>' to give the capture group a name where 'name' is a unique name.

```
([a-z0-9_\.-]+)

([\da-z\.-]+)

([a-z\.]{2,6})

```


### Bracket Expressions
Bracket expressions contain a set of character classes and are denoted by brackets '[]', hence the name. You can use the character '^' to negate the expression if desired.

```
[a-z0-9_\.-]

[\da-z\.-]

[a-z\.]

```

### Greedy and Lazy Match
Using quantifiers such as '*' '+' or '{}' makes the expression greedy because they expand the match as far as possible. If we wanted to make the expression lazy we would instead use a '?' Our regex is greedy and is using '+' in a couple of expressions as shown below. 

```
([a-z0-9_\.-]+)

([\da-z\.-]+)
```

## Advanced Regex Options
Some advanced options that are important to know but are not included in our regex sample. 

### Boundaries
Boundaries are denoted by '\b' at the beggining like anchors and are used to match whole words, everything in between the '\b'  It's also called a 'word boundary'. If you wanted to negate, you would use '\B' instead, this would only match if it's fully surrounded by word characters. The below example matches the characters 'word' 

```
\bword\b
```


### Back-references
Back references are intended to match the same text pattern as the capture group before, denoted by a number.  This is a good strategy to help reuse parts of your pattern or ensure that two capture groups match. The below example would match 'word' again. 

```
[(word)]\1
```

### Look-ahead and Look-behind
Look-ahead and Look-behind also known as 'lookaround' are treated like assertions in the start and end of a line, like anchors.  They don't match strings, only let you know that it is possible.  We use '(?=)' for looking ahead and '(?<=)' to look behind.  

- Look-ahead. The example matches 'f' only if it is followed by 'q'.
    ```
    f(?=q)
    ```

- Look-behind.  The example matches 'f' only if it is before a 'q'.
   ```
   (?,=q)f
   ```


## Author


Kat Contreras is a full stack web developer.  You can view thier [Github Profile](https://github.com/katcontrerasdev) for more information. 
