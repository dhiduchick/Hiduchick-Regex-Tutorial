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
Bracket expressions, also known as character classes, are used in regular expressions to match a single character out of a set of characters. In the context of matching URL regex, bracket expressions are used to define specific characters or ranges of characters that can appear at certain positions in the URL.

In the given URL regex expression, the following bracket expressions are used:

1. [\da-z\.-]: This bracket expression matches a single character that is a digit (\d), a lowercase letter (a-z), a dot (.), or a hyphen (-). It allows for matching characters commonly found in domain names, such as alphanumeric characters, dots, and hyphens.

2. [a-z\.]: This bracket expression matches a single lowercase letter (a-z) or a dot (.). It is used specifically to match characters in the top-level domain (TLD) part of the URL, ensuring that only lowercase letters and dots are accepted in this position.

Bracket expressions provide a concise way to specify the characters that should be matched at a particular position in the URL, allowing for flexibility and customization in regex patterns.

### The OR Operator
In regular expressions, the OR operator is represented by the vertical bar |. It allows you to specify multiple alternatives for matching patterns. In the context of matching URL regex, the OR operator can be used to define alternative patterns for specific parts of the URL.

For example, in the following URL regex: `^(https?:\/\/)?` The ? after (https?:\/\/) indicates that the s in https is optional, allowing the URL to start with either http:// or https://.

Similarly, in the following URL regex: `([a-z\.]{2,6})` The {2,6} specifies that the preceding pattern [a-z\.] should be repeated 2 to 6 times, allowing for top-level domains (TLDs) like .com, .org, .net, etc. The dot . in [a-z\.] represents the dot in the TLD, and the [a-z] matches lowercase letters. So, in this case, the OR operator is not explicitly used, but alternative patterns are achieved through the quantifier {2,6}, allowing for different TLD lengths.
### Flags
In regular expressions, flags are sued to modify the behavior of the pattern matching. For matching URL regex, some commonly used flags include:
1. i(ignore case): This flag makes the pattern matching case-insensitive, allowing it to match both uppercase and lowercase characters interchageably.
2. g(global): This flag makes the pattern search gloab within the input string, meaning it will find all occurances of the pattern rather than just the first one.
3. m(multiline): This flag modifies the behavior of ^ and $ to match the beginning and end of each line wihtin a miulti-line string, rather than just beginning and end of the entire string. 
4. s(dotALL): This flas allows the dot . to match newline characters as well, whereas by default it does not match newline characters.
5. u(unicode): This flad enables support for Unicode matching, allowing Unicode characters to be properly matched.
6. y(sticky): This flad requires that the match must start exactly at the index specified by the 'lastIndex' property of the regular expression object.

for matching URL regex, you might use flags such as 'i' to make the matching case-insensitive, or 'g' to find all occurrances of the pattern within the input string. However, the specific flags used depend on the requirement of your matching scenario.
### Character Escapes
Character Escapred in a URL regex allow you to match specific characters or character classes. Here are some common character escapes used in URL regex:
1. `\.` : Matches a literal period characters (``.`).
2. `\/`: Matches a literal forward slash character (`/`).
3. `\w`: Matches ant word character (equivalent to `[A-Za-z0-9_]`).
4. `\d`: Matches any digit character (equivalent to `[0-9]`).
5. `\s`: Matches any whitespace character.
6. `\b`: Matches a word boundary.
7. `\W`: Matches any non-word character (equivalent to `[A-Za-z0-9_]`).
8. `D`: Matches any non-digit character (equivalent to `[^0-9]`).
9. `\S`: Matches any non-whitespace character
These character escapres allow you to create more percise URL regex patterns by matching specific tpyes of charater or character classes. 
## Author
Made with ♡ by: Daelyn Hiduchick 
[Github Link](https://github.com/dhiduchick) 