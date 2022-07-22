# Regex-Tutorial: Matching an Email

Regular expressions (regex or regexp) are very useful in extracting information from any text by searching for one or more matches of a specific search pattern.  Regular expressions are part of many programming languages including JavaScript, Perl, Python, PHP, and Java, and form a language of their own. These patterns can be simple, where they match an exact string, or they can be more complex, where they match strings that contain a set of rules. One common usage for regex is for identifying whether a user has correctly entered something into a form, such as an email address. 

## Summary

This tutorial will go over the **Matching an Email** regex below:
```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```

The email regex can be separated into five separate parts, as listed below:

- The username

- An @ symbol separating the username from the domain name

- The domain name

- The dot or period separating the domain name from the domain

- The domain extension (i.e., .com, .org, .gov)

**Example Email:**

alana_harris_rules_1979@mckeel111.com

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
- [Resources](#resources)

## Regex Components

### Anchors

The Anchors in this regex tutorial are `^` and `$`, these are, as is implied by the category they are in, at the beginning and the end of the regex.
```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```

By default, the `^` match must occur at the beginning of the string. If you have a multiple line string, the match must occur at the beginning of the line. 

By default, the `$` match must occur at the end of the string or before `\n` at the end of the string. If you have a multiple line string, the match must occur at the end of the line or before `\n` at the end of the line.

### Quantifiers

Quantifies specify how many instances of a character, group, or character class must be present in the input for a match to be found. In this regex, the Quantifiers are `+` and `{2,6}`.
```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```

The `*` will match 0 or more character(s).

The `+` will match 1 or more character(s).

The `?` will match 0 or one character.

The `{n}` will match exactly `n` character(s).

The `{n,m}` quantifier will match an expression that is at least n character(s) but no more than m character(s) where `n` and `m` are integers.

### OR Operator

The OR Operator `|` can be used to match characters or expressions on either side of the `|` operator. 



### Character Classes

A character class in a regex defines a set of characters, any one of which can occur in an input strig to fulfill a match. In this regex, the `\d`, and `\.` are used as the Character Classes. The `\d` is used to specify a range `a-z`, while the `.` is used to match any character.
```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```
Additionally `\.` will match any character, except the newline character `\n\`.
Another examples is `\s`, this will match any single whitespace character, including tabs and line breaks.

### Flags

Flags are placed at the end of a regex, after the second dash, and they define additional functionality or limits for the regex. There are a total of six optional flags, however, the three most popular are below.

`g` is a Global search, this will test the regex against all possible matches in a string.

`i` is a Case-insensitive search, this means the case will be ignored will attempting a match in a string.

`m` is a Multi-line search, this will allow the regex to treat a multi-line input string as multiple lines.

### Grouping and Capturing

When placing part of a regex inside round brackets or parentheses, it groups that part of the regex together. This allows a quantifier to be applied to the entire group or restrict alternation to part of the regex.

```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```
In the above example, `([a-z0-9_\.-]+)`, `([\da-z\.-]+)`, and `([a-z\.]{2,6})` are the Groupings.

### Bracket Expressions

Anything inside of a set of square brackets represents a range of characters that will be matched. Bracket Expressions are also known as a positive character group. These expressions can be written to include all of the characters that will be matched. 

```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```

In the above example, `[a-z0-9_\.-]`, `[\da-z\.-]`, and `[a-z\.]` are Bracket Expressions.

### Greedy and Lazy Match

A non-greedy or lazy quantifier tries to match an element as few times as possible. You can turn a greedy quantifier into a lazy quantifier by simply adding a `?`.

```md
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
```
In the above example, `*` and `{}` are the Greedy Match. Below is a table of the Greedy and Lazy quantifier's.

Greedy | Lazy  | Description
-------| ------| ---------------------
|*     | *?    | Star Quantifier: 0 or more         
|+     | +?    | Plus Quantifier: 1 or more             
|?     | ??    | Optional Quantifier: 0 or 1
|{n}   | {n}?  | Quantifier: exactly n
|{n,}  | {n,}? | Quantifier: n or more
|{n,m} | {n,m}?| Quantifier: between n and m 


### Boundaries

The Word Boundary, represented as `\b`, matches positions where one side is a word character (usually a letter, digit or underscore, but there are additional variations) and the other side is not a word character (such as the beginning of a string or a space).

For example, `\bdog\b` would match brown dog, but it would not match to dogma. However, if you use `\bdog`, it would then match to dogma.

Below is a link to a Regex Cheat Sheet for additional assistance:
http://www.rexegg.com/regex-quickstart.html#anchors

### Back-references

Backreferences match the same text as previously matched by a capturing group. A backreference can be used more than one in a regex.

In the following example, three backreferences were used:
`([j-l])y\1y\1` will then match `jyjyj`, `kykyk` and `lylyl`.

### Look-ahead and Look-behind

These are known collectively as "lookaround" and are zero-length assertions, these will match characters, but return only a result, match or no match. 

Lookahead example:
`(?=element)`

Lookbehind example:
`(?<=element)`

### Resources

Below is a link to a Regex Cheat Sheet for additional assistance:
http://www.rexegg.com/regex-quickstart.html#anchors

Below is a link to a Mark Down Guide for additional assistance:
https://www.markdownguide.org/cheat-sheet/

Below is a link to a Regex playground where you can try out expressions:
https://regex101.com/

## Author

Alana McKeel | "It’s not a bug – it’s an undocumented feature." | [Github Profile](https://github.com/alanam79)