# Regex Tutorial: Matching Hexadecimal Code

## Summary

A Regular Expression or 'regex' code is a pattern of characters which is used to validate or match lengths of text, or string.

```diff
Regex example:       /^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```

This regex can be used to find all hexadecimal codes, which are made up of six alphanumeric symbols including numbers 0-9, and/or letters from A-F, following a hash. It can be broken down into several parts:

/ ... /            = forward slashes enclosing sequence.

^#                 = Caret character (followed by hashtag).

#?                 = Question mark (preceded by hashtag).

(...)              = Round brackets creating a positive Lookahead assertion. 

[...] ... [...]    = Square bracket value set.

{...}              = Curly bracket quantifier.

|                  = Pipe symbol creating a logical OR condition. 

$                  = Dollar sign metacharacter anchor. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)

## Regex Components

### Anchors

Anchors are regex tokens that don't find matches, but specify the part or position in a string that will match.

#### Caret symbol ^

Whatever character follows the caret character ^ will match sequences that begin with that character. So ^# will positively match all sequences that start with #, which includes all hexadecimal color codes starting with hash symbols.

#### Dollar Sign $

The dollar sign indicates the end of the string. The dollar sign is a meta character which doesn't form part of the matched values. 

### Quantifiers

Quantifiers specify how many instances of a part of string should be repeated in matches. 

#### Question Mark ?

If a character is followed by a question mark, it makes matching that character optional. This allows matching where there are differences in spelling or formalisation. For instance, Feb?ruary will match instances of Feb and February. Feb 10(th)? will match Feb 10 and Feb 10th.

Here, #? will allow matches of hex code which are not followed by a hash symbol.

#### Curly Brackets {...}

Curly brackets denote a quantifier used to specify the range of preceding characters that will match. For instance [a-z]{1} will match one letter from a to z.

In the above regex, the hexadecimal regex will match 6 instances of the preceding set [a-f0-9], or six symbols including letters a to z, or numbers 0 - 9. The quantifier {3} will match 3 instances of preceding values [a-f0-9].

### OR Operator

#### Pipe Symbol |

A pipe symbol creates a logical OR condition meaning 'either', and is used to match alternative values enclosed in brackets. This creates matches of either value sets. 

Here, the regex will match either 6 OR 3 values of a-f, 0-9. This will find hex codes of 6 values, as well as HEX codes that have been shortened to 3 values (e.g. #f0c, or #f0cf0c) because the first three values repeat.

### Character Classes

Character classes match a symbol of a range of enclosed characters. For instance, in the example regex, [a-f0-9] defines a class of letters from a to f, and digits from 0 to 9, and which describe the range of matches.

### Grouping and Capturing

Parts of a regex patterns can be 'grouped' by enclosing in round brackets. This allows parts of a string to be remembered and referenced again to get matches where the group repeats. In the regex example, the round brackets create a pair of capturing groups.

([a-f0-9]{6}|[a-f0-9]{3})

## Author

GitHub profile: https://github.com/sifzerda/

GitHub repo: https://github.com/sifzerda/regex-tutorial
