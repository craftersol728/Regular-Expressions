# The Amazing Regex

Regular expressions (regex) are a pattern-matching language used for searching, manipulating, and processing text data. They provide a way to match and extract specific patterns from a larger body of text, making them a powerful tool for text processing tasks such as data validation, search-and-replace operations, and information extraction. Regex are used in many programming languages, text editors, and other tools, and are especially useful for working with unstructured text data.

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

The regex i will be describing and explain is the following code below:

^([A-Z]{1}[a-z]{1,})\s([A-Z]{1}[a-z]{1,})\s([0-9]{4})\s(\b(?:(?:0?[1-9])|(?:1[0-2]))

The 1st part of this code ^([A-Z]{1}[a-z]{1,}) "^" indicates the start of the string, and the parentheses '()' is a capturing group, and a capturing group in a Regex is it allows me to extract a portion of hte text that matches the pattern inside the parentheses as a seperate value.

So, this part of the regex would match sequences like "John", "Alice", "Michael", etc. and allow you to extract the matched text as a separate value, such as the name of a person.

The 2nd portion of the regex \s([A-Z]{1}[a-z]{1,}) matches a sequence of characters that starts with a white-space character (\s) followed by a capital letter ([A-Z]{1}) and one or more lowercase letters ([a-z]{1,}).

The portion of the regex \s([0-9]{4}) matches a sequence of characters that starts with a white-space character (\s) followed by exactly four digits ([0-9]{4}).As in the previous examples, the parentheses ( ) define a capturing group, which allows you to extract the matched text as a separate value.

The pattern inside the capturing group uses several regular expression features, such as a non-capturing group (?:), an alternation (|), and an optional match (?).

The first alternative (?:0?[1-9]) matches an optional zero (0?) followed by a digit in the range 1 to 9. The second alternative (?:1[0-2]) matches a digit 1 followed by a digit in the range 0 to 2. The non-capturing group (?: ) is used to group the alternatives and make the alternation (|) apply to the whole group.

An example of a string that would match this regex is "John Doe 2022 12", where:

    The first capturing group ([A-Z]{1}[a-z]{1,}) matches "John"
    The second capturing group ([A-Z]{1}[a-z]{1,}) matches "Doe"
    The third capturing group ([0-9]{4}) matches "2022"
    The fourth capturing group (\b(?:(?:0?[1-9])|(?:1[0-2]))) matches "12"

So, the matched string represents the name, surname, year, and month respectively. The matched values could be used for further processing or manipulation.
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
A regular expression, or regex for short, is a pattern that defines a set of strings. The pattern is composed of various components, each with a specific meaning and purpose. Some common components used in regex include:

    Literal characters: These are plain characters that match themselves, such as letters, digits, and punctuation. For example, the regex abc matches the string abc.

    Character classes: These are used to match any single character from a set of characters. For example, the regex [abc] matches any single character that is either a, b, or c.

    Anchors: These are special characters that match the position of the string, rather than the characters themselves. For example, the caret (^) matches the start of the string, and the dollar sign ($) matches the end of the string.

    Quantifiers: These are used to specify the number of times a pattern should be repeated. For example, the asterisk (*) matches zero or more repetitions of the preceding pattern, and the plus sign (+) matches one or more repetitions of the preceding pattern.

    Groups: These are used to group together parts of a pattern and capture the matched text. For example, the regex (abc) matches the string abc and captures it, so that it can be used later.

    Alternation: This is used to match one of several alternative patterns. For example, the regex abc|def matches either the string abc or the string def.

These are just a few of the components that can be used in a regex. Different programming languages may have slightly different implementations and variations, but the basic components are often similar.
### Anchors
Anchors in regular expressions (regex) are special characters that match the position of the string, rather than the characters themselves. They allow you to define the pattern in a more precise manner. Some common anchors used in regex include:

    Caret (^): Matches the start of the string. For example, the regex ^A matches any string that starts with the letter A.

    Dollar sign ($): Matches the end of the string. For example, the regex t$ matches any string that ends with the letter t.

    Word boundary (\b): Matches a position between a word character (letter, digit, or underscore) and a non-word character. For example, the regex \bthe\b matches the word the when it appears as a complete word.

    Word start (\A): Matches the start of the string, ignoring any leading whitespace characters.

    Word end (\z): Matches the end of the string, ignoring any trailing whitespace characters.

Anchors are powerful tools that can be used to define the pattern more precisely and to ensure that the pattern matches only the desired parts of the string. However, they should be used with care, as they can also make the pattern more restrictive and cause it to miss valid matches.
### Quantifiers
Quantifiers in regular expressions (regex) are used to specify the number of times a pattern should be repeated. They allow you to define the pattern more precisely, depending on the number of repetitions that you want to match. Some common quantifiers used in regex include:

    Asterisk (*): Matches zero or more repetitions of the preceding pattern. For example, the regex A* matches any number of A characters, including zero.

    Plus sign (+): Matches one or more repetitions of the preceding pattern. For example, the regex A+ matches one or more A characters.

    Question mark (?): Matches zero or one repetition of the preceding pattern. For example, the regex A? matches either an A character or no A character.

    Braces ({n}): Matches exactly n repetitions of the preceding pattern. For example, the regex A{3} matches exactly three A characters.

    Braces with a minimum and maximum ({n,m}): Matches at least n and at most m repetitions of the preceding pattern. For example, the regex A{2,4} matches two to four A characters.

Quantifiers are useful for matching repeated patterns in a string, such as multiple words, multiple digits, or multiple punctuation marks. However, they should be used with care, as they can also make the pattern more restrictive and cause it to miss valid matches. Additionally, some quantifiers can cause the regex engine to become slow or even to fail if the pattern is too complex or if the input string is too long.
### OR Operator
The OR operator in regular expressions (regex) is used to match one of several possible patterns. It allows you to specify multiple alternative patterns, and the regex engine will match the first pattern that it finds in the input string. The OR operator is represented by the vertical bar (|).

For example, the regex A|B matches either the letter A or the letter B. If the input string is AB, the regex engine will match the first A character. If the input string is BA, the regex engine will match the first B character.

The OR operator is useful for matching one of several possible patterns, such as multiple words, multiple digits, or multiple punctuation marks. It is also useful for matching patterns that can appear in different forms, such as date formats, phone numbers, or email addresses. However, the OR operator should be used with care, as it can make the pattern more complex and harder to understand. Additionally, the OR operator can cause the regex engine to become slow or even to fail if the pattern is too complex or if the input string is too long.
### Character Classes
Character classes in regular expressions (regex) are used to match specific sets of characters. They allow you to define a pattern based on the type of characters that you want to match, rather than matching specific characters. Character classes are represented by square brackets ([]).

For example, the regex [0123456789] matches any digit from 0 to 9. If the input string is 12345, the regex engine will match all five characters.

There are several special characters that can be used inside character classes to match specific types of characters, such as digits, letters, or punctuation marks. Some common character classes include:

    \d: Matches any digit (equivalent to [0-9])

    \w: Matches any word character (letters, digits, or underscores)

    \s: Matches any whitespace character (spaces, tabs, or line breaks)

    \D: Matches any character that is not a digit (equivalent to [^0-9])

    \W: Matches any character that is not a word character (equivalent to [^a-zA-Z0-9_])

    \S: Matches any character that is not a whitespace character (equivalent to [^\s])

Character classes are useful for matching specific sets of characters, such as numbers, letters, or punctuation marks. They are also useful for matching patterns that can appear in different forms, such as date formats, phone numbers, or email addresses. However, character classes should be used with care, as they can make the pattern more complex and harder to understand. Additionally, character classes can cause the regex engine to become slow or even to fail if the pattern is too complex or if the input string is too long.
### Flags
Flags in regular expressions (regex) are used to modify the behavior of the regex engine. They are optional parameters that are placed after the regular expression pattern to change how the pattern is interpreted or how the matches are returned.

Some common flags in regex include:

    i: Makes the match case-insensitive. For example, the regex /a/i matches both a and A.

    g: Makes the match global. This means that the regex engine will continue searching for matches after finding the first match. By default, the regex engine stops after finding the first match.

    m: Makes the match multiline. This means that the ^ and $ anchors match the start and end of a line, rather than the start and end of the input string.

    s: Makes the dot (.) match all characters, including newline characters. By default, the dot only matches characters other than newline characters.

    u: Enables Unicode support. This means that the regex engine will interpret the pattern as a sequence of Unicode characters, rather than a sequence of bytes or ASCII characters.

You can use multiple flags together by concatenating them. For example, the regex /a/ig is a case-insensitive global search for the letter a.

Flags are useful for customizing the behavior of the regex engine to meet your specific needs. However, they should be used with care, as they can make the pattern more complex and harder to understand. Additionally, flags can cause the regex engine to become slow or even to fail if the pattern is too complex or if the input string is too long.

(im too dumb to understand section)

Okay, let's pretend you have a big bag of toys and you want to find a specific toy. The toy's name is written on a piece of paper. That piece of paper is like a pattern for finding the toy.

Regex flags are like special instructions that tell the toy finder how to search for the toy in the big bag. For example, if you want the toy finder to only search for the toy when its name is written in uppercase letters, you would use the "case-insensitive" flag. This means the toy finder would still find the toy even if its name is written in lowercase letters.

Another flag is the "global" flag. This means that if there are multiple toys with the same name, the toy finder will find all of them and not just the first one it comes across.

There are other flags as well, each with its own special instruction. By using these flags, you can help the toy finder find the toy you're looking for more easily and correctly.
### Grouping and Capturing

Grouping and capturing in regular expressions (regex) allow you to group together multiple characters or patterns into a single unit, and capture the matched text as a separate entity that can be referenced later in your code.

Think of it like a toy box. The toy box is a group that contains multiple toys. Each toy can be captured and taken out of the box separately.

In regex, you can use parentheses ( ) to group together multiple characters or patterns. For example, the regex (ab)+ matches one or more occurrences of the string ab. The parentheses group together the characters a and b into a single unit.

Capturing allows you to reference the text that is matched by the group in your code. For example, if the string abc is matched by the regex (ab)+, you can reference the text ab that was captured by the group in your code. This can be useful for extracting specific parts of a string or for creating more complex patterns.

In short, grouping and capturing allow you to work with multiple characters or patterns as a single unit, and to capture the matched text as a separate entity that can be referenced later in your code.

The grouped and captured information in regular expressions (regex) can be used in various ways, depending on the programming language and the context in which the regex is being used. Some common uses of grouped and captured information include:

Extracting specific parts of a string: You can use capturing groups to extract specific parts of a string that match a certain pattern. For example, you can use regex to extract all the email addresses from a list of text.

Replacing parts of a string: You can use capturing groups to replace specific parts of a string with new text. For example, you can use regex to replace all the phone numbers in a list of text with asterisks.

Validating user input: You can use regex to validate user input and ensure that it matches a certain pattern. For example, you can use regex to ensure that a user enters a valid email address.

Parsing data: You can use regex to parse data in a structured format, such as a CSV file or an XML document. For example, you can use regex to extract all the rows from a CSV file.

Conditional statements: You can use capturing groups to conditionally match text based on its content. For example, you can use regex to match a string that starts with a certain word, but only if the string contains a certain number of characters.

These are just a few examples of what you can do with grouped and captured information in regex. The possibilities are virtually limitless, and the use of regex can greatly simplify many text processing tasks.

### Bracket Expressions
Bracket expressions are a special type of character class in regular expressions (regex) that allow you to match any character that is listed inside the brackets. Bracket expressions are represented by square brackets [ ].

For example, the regex [aeiou] matches any one of the characters a, e, i, o, or u. The regex [0-9] matches any digit from 0 to 9. The regex [a-zA-Z0-9] matches any alphanumeric character, i.e., any letter or digit.

You can also use negated bracket expressions to match any character that is not listed inside the brackets. For example, the regex [^aeiou] matches any character that is not a, e, i, o, or u. The regex [^0-9] matches any character that is not a digit.

Bracket expressions are useful for matching specific characters or ranges of characters in a string, and they can greatly simplify many text processing tasks. They can also be combined with other regex constructs, such as quantifiers, to create more complex patterns.
### Greedy and Lazy Match
In regular expressions (regex), "greedy" and "lazy" are terms that describe the behavior of quantifiers when matching text. Quantifiers are symbols such as *, +, ?, and {n,m} that specify how many times a preceding character or group should be matched.

A "greedy" quantifier will match as much text as possible, up to the maximum number of times specified by the quantifier. For example, the regex .* with a greedy quantifier will match any sequence of characters, from zero to an unlimited number of characters. This means that if the regex is applied to a string, it will match the entire string.

A "lazy" quantifier, on the other hand, will match as little text as possible, up to the minimum number of times specified by the quantifier. For example, the regex .*? with a lazy quantifier will match any sequence of characters, but only up to the first character that doesn't match. This means that if the regex is applied to a string, it will only match the minimum possible portion of the string that satisfies the pattern.

In general, the choice between a greedy and a lazy quantifier depends on the desired behavior for the particular regex. Greedy quantifiers are often used when the goal is to match as much text as possible, while lazy quantifiers are used when the goal is to match only the minimum necessary portion of the text. By understanding the behavior of greedy and lazy quantifiers, you can create more complex and sophisticated regex patterns.
### Boundaries
In regular expressions (regex), "boundaries" are special characters or sequences of characters that define the beginning or end of a word, a line, or some other text element. Boundaries are used to limit the scope of a regex match and to ensure that the match occurs at a specific location within the text.

Some common boundary characters include:

    ^: Matches the beginning of a line.
    $: Matches the end of a line.
    \b: Matches a word boundary, i.e., the position between a word character (such as a letter or digit) and a non-word character (such as a space or punctuation mark).
    \B: Matches a non-word boundary, i.e., any position that is not a word boundary.

For example, the regex ^[A-Z] matches the beginning of a line followed by an uppercase letter. The regex [0-9]$ matches any digit. The regex \b[A-Z][a-z]+\b` matches any word that starts with an uppercase letter and is followed by one or more lowercase letters.

By using boundaries in your regex patterns, you can create more precise and accurate matches, and ensure that your regex only matches the desired text elements.
### Back-references
Back-references in regular expressions (regex) are a way to refer back to a previously matched group within the same regex pattern. They allow you to reuse the matched text in a subsequent part of the pattern, making it easier to define complex patterns that are based on the relationship between multiple groups of text.

A back-reference is represented by a backslash followed by a number that corresponds to the group number of the desired match. For example, the syntax \1 refers to the first captured group, \2 refers to the second captured group, and so on.

Here's a simple example that demonstrates the use of back-references:

regex pattern: (\w+)\s\1

text: "the the"

match: "the the"

In this example, the regex pattern (\w+)\s\1 matches any word that is followed by a space and then the same word. The first captured group (\w+) matches the first word, and the back-reference \1 matches the second word, ensuring that it is the same as the first word.

Back-references can be very useful when you want to match patterns that repeat or have a certain relationship between multiple parts of the text. They are a powerful tool for text processing and pattern matching.
### Look-ahead and Look-behind
Lookahead and lookbehind, collectively called “lookaround”, are zero-length assertions just like the start and end of line, and start and end of word anchors explained earlier in this tutorial. The difference is that lookaround actually matches characters, but then gives up the match, returning only the result: match or no match. That is why they are called “assertions”. They do not consume characters in the string, but only assert whether a match is possible or not. Lookaround allows you to create regular expressions that are impossible to create without them, or that would get very longwinded without them.

there is positive and negative look aheads Negative lookahead is indispensable if you want to match something not followed by something else. When explaining character classes, this tutorial explained why you cannot use a negated character class to match a q not followed by a u. Negative lookahead provides the solution: q(?!u). The negative lookahead construct is the pair of parentheses, with the opening parenthesis followed by a question mark and an exclamation point. Inside the lookahead, we have the trivial regex u.

Positive lookahead works just the same. q(?=u) matches a q that is followed by a u, without making the u part of the match. The positive lookahead construct is a pair of parentheses, with the opening parenthesis followed by a question mark and an equals sign.

You can use any regular expression inside the lookahead (but not lookbehind, as explained below). Any valid regular expression can be used inside the lookahead. If it contains capturing groups then those groups will capture as normal and backreferences to them will work normally, even outside the lookahead. (The only exception is Tcl, which treats all groups inside lookahead as non-capturing.) The lookahead itself is not a capturing group. It is not included in the count towards numbering the backreferences. If you want to store the match of the regex inside a lookahead, you have to put capturing parentheses around the regex inside the lookahead, like this: (?=(regex)). The other way around will not work, because the lookahead will already have discarded the regex match by the time the capturing group is to store its match.
## Author

https://github.com/craftersol728

