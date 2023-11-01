# Title (replace with your title)

This guide aims to provide a clear explanation of regular expressions (Regex) and how to utilize them. Regular expressions are a powerful tool for identifying specific patterns of characters within a text. They are invaluable for tasks like extracting information from text or validating input. In this tutorial, we'll focus on a practical example of using regular expressions to match an email address. We'll break down the various components that make up regular expressions for a better understanding.

## Summary

Throughout this tutorial, we will refer to the following code as an example of how different regex components can be applied. This particular code is designed for matching email addresses, and its primary purpose is to validate whether an email adheres to the correct format.

Here is the code for matching emails:

/^[\w-]+(\.[\w-]+)*@[\w-]+(\.[\w-]+)*(\.[a-zA-Z]|{2,7})$/

In summary, this regular expression is designed to validate email addresses with the following format: "mail@domain.com".

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
^ and $
^ marks the position at the start of a line. 
$ marks the position at the end of a line. 

But when they are together, they ensure that the pattern matches an entire line: from start to finish like in this case.


### Quantifiers

Quantifiers are used to specify the number of times a character or a group of characters should be repeated in the matching pattern.

[\w-]+  
Matches one or more word characters (letters, digits, or underscores) or hyphens.
The + quantifier specifies that one or more word characters or hyphens must be matched.

(\.[\w-]+)* - Matches a dot followed by one or more word characters or hyphens, and this group can be repeated zero or more times.
The * quantifier after the parentheses group specifies that this group can occur zero or more times.

(\.[a-zA-Z]|{2,7}) - Matches a dot followed by a lowercase or uppercase letter, and this group can be repeated between 2 and 7 times.
{2,7} quantifier specifies that this group must be repeated between 2 and 7 times.
This creates a minimum and a maximum for how long the top level domain can be (ex .com, .ex, .mx).

### Grouping Constructs

In regular expressions, grouping constructs are used to group multiple characters, symbols, or subpatterns together within a pattern. These groups are enclosed within parentheses (). Grouping constructs serve several important purposes, they alllow u to apply logic to groups of characters.

In our example expression, we have two forms of grouping
Grouping for Domain and Subdomains:
(\.[\w-]+)*

Grouping for Top-Level Domain:
(\.[a-zA-Z]|{2,7})

### Bracket Expressions

Bracket expressions, also known as character classes, are a way to specify a set of characters that you want to match within a regular expression. They allow you to define a range of characters that can appear at a specific position in the pattern. Here's a general description and how they are used in the provided regular expression:

In the regular expression /^[\w-]+(\.[\w-]+)*@[\w-]+(\.[\w-]+)*(\.[a-zA-Z]|{2,7})$/:

[\w-]: This character class, [\w-], matches any word character (alphanumeric or underscore) or a hyphen. It allows any combination of these characters to be matched.

[...]: This square bracket notation defines a character class. The characters within these brackets represent a set of characters you want to match.

{2,7}: This quantifier indicates that the previous character class ([a-zA-Z]) should match between 2 and 7 times. This enforces that the domain extension (like ".com" or ".edu") should have a length between 2 and 7 characters.

### Character Classes

Character classes allow you to define a range of characters, and the regular expression engine matches any character within that range.

[\w-]: This character class matches any word character (alphanumeric or underscore) or a hyphen. It allows any combination of these characters to be matched in the username part of the email.

[\w-]: This character class appears in multiple places in the regular expression, matching word characters or hyphens within the domain part of the email. These character classes ensure that the username and domain can contain alphanumeric characters, underscores, and hyphens.

[a-zA-Z]: This character class matches any uppercase or lowercase letter (from 'a' to 'z' and 'A' to 'Z). It specifies that the last part of the email domain should consist of letters.

### The OR Operator

The OR operator is represented by the pipe symbol "|"
It allows you to specify multiple alternatives for a match. In the given regular expression

The OR operator can be found in this part:

(\.[a-zA-Z]|{2,7})

### Flags

In our example regular expression, /^[\w-]+(\.[\w-]+)*@[\w-]+(\.[\w-]+)*(\.[a-zA-Z]|{2,7})$/, doesn't utilize any flags. However, flags in regular expressions are parameters appended after the final / and are employed to alter the way the search is performed.

Typical flags encompass "i," which stands for case-insensitive matching, "g," used for global matching, and "m," employed for multi-line matching. Thers also "S", "Y" and "U".

### Character Escapes

Escape characters in regular expressions are used to indicate that a character should be treated as a literal character rather than as a part of the regular expression pattern. They are typically represented by a backslash \ followed by the character to be escaped. For example, \. would escape the period character so that it matches a literal period, not any character as it would without the escape character.

Here are a few common escape characters and their meanings:

\.: Escapes a period to match a literal period.
\\: Escapes a backslash to match a literal backslash.
\*: Escapes an asterisk to match a literal asterisk.
\( and \): Escapes parentheses to match them literally.
Using escape characters is important when you want to search for specific characters that have special meanings in regular expressions, ensuring they are treated as regular characters.

## Author

My GitHub profile: https://github.com/jalpiva98

