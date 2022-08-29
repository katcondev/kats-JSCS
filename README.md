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
    ```

    ```
    [\da-z\.-]+
    ```

- The second set, or third quantifier is '{2,6}' Match everything with a character between two and six times, as many as possible. This gives a set range. 

    ```
    [a-z\.]{2,6}
    ```

### OR Operator


### Character Classes


### Flags


### Grouping and Capturing


### Bracket Expressions


### Greedy and Lazy Match


### Boundaries


### Back-references


### Look-ahead and Look-behind




## Author


Kat Contreras is a full stack web developer.  You can view thier [Github Profile](https://github.com/katcontrerasdev) for more information. 
