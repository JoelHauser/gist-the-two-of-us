# Gist the two of us

## Summary

A regular expression (shortened as regex or regexp;[1] sometimes referred to as rational expression[2][3]) is a sequence of characters that specifies a search pattern in text. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings, or for input validation. Regular expression techniques are developed in theoretical computer science and formal language theory.

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
Anchors are a different breed. They do not match any character at all. Instead, they match a position before, after, or between characters. They can be used to “anchor” the regex match at a certain position. The caret ^ matches the position before the first character in the string. Applying ^a to abc matches a. ^b does not match abc at all, because the b cannot be matched right after the start of the string, matched by ^. See below for the inside view of the regex engine.

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. The following table lists the quantifiers supported by .NET.

### OR Operator
Grouping and alternation are core features of every modern regular expression library. You can provide as many terms as desired, as long as they are separated with the pipe character: |. This character separates terms contained within each (...) group.

^I love (cats|dogs), but not (polar bears|snakes).$
### Character Classes
With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. Simply place the characters you want to match between square brackets. If you want to match an a or an e, use [ae]. You could use this in gr[ae]y to match either gray or grey.

### Flags
Regular expressions may have flags that affect the search.

There are only 6 of them in JavaScript:

i
With this flag the search is case-insensitive: no difference between A and a.

g
With this flag the search looks for all matches, without it – only the first match is returned.

m
Multiline mode.

s
Enables “dotall” mode, that allows a dot . to match newline character \n.

u
Enables full Unicode support. The flag enables correct processing of surrogate pairs

y
“Sticky” mode: searching at the exact position in the text.

### Grouping and Capturing
Groups use the ( ) symbols (like alternations, but the | symbol is not needed). They are useful for creating blocks of patterns, so you can apply repetitions or other modifiers to them as a whole. In the pattern ([a-x]{3}[0-9])+, the + metacharacter is applied to the whole group.

Also, another main use of groups is for processing parts of a match like extracting data or replacing it.

### Bracket Expressions
Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

'elephant'.match(/[abcd]/) // -> matches 'a'
You can use the ^ metacharacter to negate what is between the brackets.

'donkey'.match(/[^abcd]/) // -> matches 'o'

You will often see ranges of the alphabet or all numerals. [A-Za-z] [0-9] Remember that these character sets are case sensitive, unless you set the i flag.

### Greedy and Lazy Match
By default, a quantifier tells the engine to match as many instances of its quantified token or subpattern as possible. This behavior is called greedy. In contrast to the standard greedy quantifier, which eats up as many instances of the quantified token as possible, a lazy (sometimes called reluctant) quantifier tells the engine to match as few of the quantified tokens as needed. As you'll see in the table below, a regular quantifier is made lazy by appending a ? question mark to it.

### Boundaries
Simply put: \b allows you to perform a “whole words only” search using a regular expression in the form of \bword\b. A “word character” is a character that can be used to form words. All characters that are not “word characters” are “non-word characters”.

### Back-references
Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag.

### Look-ahead and Look-behind
Lookahead and lookbehind, collectively called “lookaround”, are zero-length assertions just like the start and end of line, and start and end of word anchors explained earlier in this tutorial. The difference is that lookaround actually matches characters, but then gives up the match, returning only the result: match or no match. That is why they are called “assertions”.

## Author
My name is Joel Hauser a Michigan State coding bootcamp student. Here I took a deep dive into the world of Regex and gist! Hopefully this was helpful to you! Feel free to checkout my other projects [Here](https://github.com/JoelHauser).
