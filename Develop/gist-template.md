# Title (replace with your title)

A Regular Expression (or “regex” for short) a sequence of characters that defines a search pattern, mainly used in "find and replace"-like operations like pattern matching. Regex can be helpful in many different ways like verifying contact information inputted into forms or matching urls in saved search histories.. In this tutorial, we will be focusing on matching a url.

## Summary

Regex uses a pattern of characters to define a specific search. With a matching URL regex, regex matches any valid URL that is written using the predefined character set.  This regex answers the most important question: Is the input URL valid?

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

While this expression may seem vague when first encountered, once it is broken down it is easy to see how the sequence works.
Components needed are:
the initial HyperText Transfer Protocol (HTTP)
the domain name (e.g. www.google, or pets): ([\da-z\.-]+)\.
the top level domain (.com, .gov, etc): ([a-z\.]{2,6})
the file path: ([\/\w \.-]*)*


### Anchors

The two principal anchors in this regex expression are the ^ at the beginning and the $ at the end.  These two expressions represent an exact string match with the components included between the two anchors.  However, these expressions can also be used by themselves. When used alone, the ^ anchor matches any string that begins with the characters following the anchor. The $ matches any string that ends with the characters that come before it. By enclosing the regex between these two anchors, we are asking the search function to match the exact string that is in between the two anchors.

### Quantifiers

You may see that some of the components of the above groups end with a ? or a *. These are known as quantifiers. Quantifiers are used to define the number of times a given expression may be identified. The ? makes a single instance of the character preceding the quantifier optional, whereas the * makes multiple instances of the characters preceding the quantifier optional. 


Let’s look at a quick example using HTTP/HTTPS:

Generally, http will contain two ? quantifiers as this expression is looking for an http:// OR an https://. In other words, a valid URL may begin with http:// OR https://, or it may not begin with either of them at all (the input begins with www.). The same applies for the / at the very end of the expression.


### OR Operator

The most common OR operator used in URL Matching is []. Using this expression will return a valid match for any characters or character classes that fall in between the brackets. 


### Character Classes

Characters in regex are categorised into character classes. The main two in our regex are;
\d matches single digit characters.
\w matches any word character, including any character or number, and underscores (/\w/ accepts 1, a, _, but not !).

There are also inverse character classes, which would be uppercase versions of previous classes \D, \W.  \D matches any non single digit characters, like whitespace or word characters.  \W matches any non-word character, like single digits or whitespace.


### Flags

Regular expressions begin and end with a “/”. So what happens if you need extra rules that fall outside of the regex?  

Flags can be used to define any extra rules that may not necessarily fit within a regex pattern.  Flags can be used to denote things like case-sensitivity, multiline matches, etc..


### Grouping and Capturing

What if we want to capture a certain pattern instead of a single character or expression?  We can use something called grouping. Grouping is when the expression is surrounded by parentheses like this: /(...)/. This is often used when a developer wants to append something to an entire group instead of a singular character.


### Bracket Expressions

Bracket expressions are similar to the OR operator; the regular expression accepts any character included inside an opening and closing bracket /[...]/.


### Greedy and Lazy Match

Lazy
?: this character only captures one (or none!) instance of any pattern before this character. We call it “lazy” because the ? doesn't read until the very end of the input.

Greedy
+ * or {}: these characters are considered greedy since they read all the way up until the very end of the string.


### Boundaries

We use boundaries when we're looking for whole words. If we want to search for a whole word, we surround it with \b/  It is similar to using quotations on search engines to find entire strings.


### Back-references

Backreferences match the same text as previously matched by a capturing group.  What does this mean in practice?  Let’s say you wanted to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag.  These are often used when modifying a complex regular expression as they make it easy for the developer to reuse the reference.

It is important to note that backreferences will never be permanently saved in the regular expression. Regex will use the last match saved into the backreference each time it needs to be used. If a new match is found by capturing parentheses, the previously saved match is overwritten.


### Look-ahead and Look-behind

To find patterns that are next to each other, we can use look-ahead and look-behind. Look-ahead, using ?=  will look left while it searches for valid patterns. Look-behind using ?<=  will look for a pattern to follow the character.

## Author

David Sklar 


GitHub:https://github.com/davidhsklar
