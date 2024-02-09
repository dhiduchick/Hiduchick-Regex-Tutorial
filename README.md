# Hiduchick-Regex-Tutorial
# Matching URL Regex



## Summary
Regular expressions (regex) play a vital role in parsing and validating text patterns within strings, and one common use case is matching URLs. A URL (Uniform Resource Locator) is a reference to a web resource that specifies its location on a computer network and a mechanism for retrieving it. Matching URL regex involves crafting a regular expression pattern that can accurately identify and extract URLs from text data. This task is particularly useful in web development, data extraction, and content analysis, where parsing and processing URLs are essential for various operations such as data scraping, link analysis, and routing in web applications. In this tutorial, we will delve into the intricacies of constructing and understanding a regex pattern specifically tailored for matching URLs, breaking down each component of the expression to provide a comprehensive understanding of its functionality and usage.


`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

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
Anchors serve as markers indicating the beginning and end points for the regular expression search. The "^" symbol signifies a match at the start of a string, while the "$" symbol denotes a match at the end. When used together, they signify that the entire string must precisely match the pattern enclosed between them, creating a requirement for an exact string match. In the given expression, the combination of both "^" and "$" anchors ensures an exact match for the entire collection of meta characters, thereby constraining the search to exact matches only.

### Quantifiers
-Quantifiers dictate the number of occurrences of a character, group, or character class within the expression. This character combination encompasses various quantifiers, which are elaborated upon in the table of contents for further understanding of groups, capturing, and brackets.

-The * symbol matches anything preceding it zero to infinite times, depending on the occurrences in the string. Within the third capture group, "([/\w .-])*", it searches for instances of the specified criteria within the brackets and then allows for the repetition of those criteria, including the potential for zero occurrences.

-The "+" symbol matches one or more occurrences, excluding zero occurrences. In the capture group "([\da-z.-]+)", the "+" symbol matches any number of instances as declared within the square brackets, ensuring at least one occurrence.

-The "?" symbol matches zero or one occurrence. For instance, the first capture group "(https?://)?" accepts either zero or one instance of "s".

-The "{}" quantifier specifies the number of occurrences of the preceding group or character. Within the last capture group, "([a-z.]{2,6})", the "{2,6}" expression seeks 2 to 6 instances of the character based on the criteria defined within the square brackets.

### Grouping Constructs
A capture group treats everything within the parentheses as a single unit, allowing the regex engine to capture and remember the matched substring for later use. In the given URL regex expression, there are four instances of capture groups:

1. Capture Group #1 (Protocol): (https?:\/\/)?
    * This group captures the protocol part of the URL (e.g., http:// or https://). It matches http:// or https:// optionally (zero or one occurrence).
2. Capture Group #2 (Domain): ([\da-z\.-]+)\.
    * This group captures the domain name of the URL. It matches one or more characters that are digits (\d), lowercase letters (a-z), dots (.), or hyphens (-) followed by a dot (.).
3. Capture Group #3 (TLD): ([a-z\.]{2,6})
    * This group captures the top-level domain (TLD) part of the URL. It matches lowercase letters (a-z) or dots (.) with a length between 2 and 6 characters.
4. Capture Group #4 (Path): ([\/\w \.-]*)*
    * This group captures the path part of the URL. It matches zero or more occurrences of characters that are forward slashes (/), word characters (\w), spaces ( ), dots (.), or hyphens (-). The * quantifier allows for flexibility in matching the path.
For instance #1, the capture group (https?:\/\/)? will include http:// or https:// in this group when searching, with the ? quantifier indicating that the s after http is optional. This ensures that both http:// and https:// protocols are captured if present in the URL.
### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)