# Regex Tutorial - Matching An Email

A regular expression is a sequence of characters that defines a search pattern. This is commonly used to find patterns within a string, find/replace characters within a string or validate input. This tutortial will go walk through the components of a regex and how it applies to matching an email.

## Summary

- Below is the regex used for validating an email address.
- In this tutorial, we will breakdown each part of the express and describing what it does.
  ```
  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/.
  ```

## Table of Contents

- [Breakdown](#breakdown)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Author](#author)
- [Questions](#questions)

## Breakdown

Quick breakdown of each section of the regex: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. `

```
/^
```

- **/** Editor command for search
- **^** Starting position within the string

```
([a-z0-9_\.-]+)
```

- Defines the search pattern in the email `brianalegre`@gmail.com
- **( )** Defines the scope
- **[ ]** Matches a single character that is contained within the brackets
- **a-z** Character range of lowercase 'a' to lowercase 'z'
- **0-9** Number range of '0' to '9'
- `_\.-` Defines the special characters that are allowed in the string `_ . -`
- **+** Match as much of the string as possible

```
@
```

- Defines the search pattern in the email brianalegre`@`gmail.com
- **@** Matches the '@' in that placement of the search

```
([\da-z\.-]+)
```

- Defines the search pattern in the email brianalegre@`gmail`.com
- **( )** Defines the scope
- **[ ]** Matches a single character that is contained within the brackets
- **\d** Matches a single characters that is a digit from 0-9
- **a-z** Character range of lowercase 'a' to lowercase 'z'
- `_\.-` Defines the special characters that are allowed in the string `_ . -`
- **+** Match as much of the string as possible

```
\.
```

- Defines the search pattern in the email brianalegre@gmail`.`com
- `\.` Matches the '.' in that placement of the search

```
([a-z\.]{2,6})
```

- Defines the search pattern in the email brianalegre@gmail.`com`
- **( )** Defines the scope
- **[ ]** Matches a single character that is contained within the brackets
- **a-z** Character range of lowercase 'a' to lowercase 'z'
- `\.` Defines the special characters that is allowed in the string `.`
- **{2,6}** Defines '2' to '6' times

```
$/.
```

**$/.** Ending position within the string

## Regex Components

### Anchors

- The anchors used in this regex expression for matching an email are `^ `, which indicates the beginning of the string and `$`to indicate the ending of the string

### Quantifiers

- Quantifiers specify how many times a character, group, or character class must be present in the input for a match to be found. Here the `+` represents one or more times and the `{2,6}` represent two to six times

### Grouping Constructs

There are three grouping construtions in the regex, each being defined with the **( )**:

- `([a-z0-9_\.-]+)` Matches the user's email name, `brianalegre`@gmail.com
- `([\da-z\.-]+)` Match the email provider, brianalegre@`gmail`.com
- `([a-z\.]{2,6})` Match the email provider's TLD, brianalegre@gmail.`com`

### Bracket Expressions

- Bracked expressios for email validation includes the character sets of `[a-z0-9_\.-]`, which is matching any letter a-z and is case senstive. It also matches a character 0-9 and matches the characters "\_" , "-" , and "."; `[\da-z\.-]`, which is matching a single digit from 0-9, any lowercase character a-z, and the characters "." and "-".; `[a-z\.]` matches any lowercase character a-z and the character ".".

### Character Classes

- The character class in this expression is `\d`, which matches a single characters that is a digit from 0-9. It will only match a single digit such as "4", but not "44".

### Greedy and Lazy Match

- This regrex includes greedy matches. Since it includes the `+` Quantifier, it will match as many times as possible giving back as needed. Another greedy Quantifier used in this regex is `{}` when matching `{2,6} for the last capture group.

## Author

- Jasmine Tsao
- Github Username: jasmineranay
- Github Link: https://github.com/jasmineranay

