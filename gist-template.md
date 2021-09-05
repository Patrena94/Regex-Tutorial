# How to Validate an Email address Tutorial

An individual that possesses an on-line account know the importance of having their email address validated for access to accounts that may contain sensitive information.  Thus, this is an important expression that a developer is required to build into the application, in order to protect their user personal contact information and financial information. As well as to ensure that communication with their users are being accessed by the appropriate individual.  

## Summary

The regular expression that we will be evaluating in this tutorial is Email validation (/^([a-z0-9_\.- ]+)@([ \da-z\.-]+)\.([a-z\.]{2,6})$/ ).

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
- [Sources and References](#Sources-and-References)

## Regex Components
Regular expression components consist of syntax that developer can use to specify patterns foun in log file records when configuring various WebTrends Analytic advanced features such as matching email address and verify URL parameters through the utilization of regular expressions to establish more flexible and powerful pattern matching than you can achieve with wildcards. regular expression are most efficient when the caret(^) is utilized at the begining of the string and the ($) is utilized at the end of the string.

### Anchors
The developer can opt to utilize the caret (^) as anchor to validate an email.  The ^ determines the position before the first character in specified string.
A developer can opt to utilize the metacharacter (\b) as anchor to validate an email. The \b determines the position before the first character in a string and after the last character in the string if the character is a word.  Or between two characters in the string, that contains a word character and null word character.
The caret (^) and metacharacter(\b) will both return a match of zero-length. Since the first character matched,  the subsequent data token is advance, and the email address is allow to match and empty string and the search is determined to be successful.

### Quantifiers
A developer will need to create the proper quantifier to resolve the issue of an empty string.  The developer can start by requiring at least one digit(alphnumeric) be entered.  The code should be similar to ^\d+$. This expression prevents your regex from finding zero length.
-^: matches the start of a line
-$: matches the end of a line
-	/^([a-z0-9_\.- ]+): implies that the email address must start with an alphanumeric character(either a lower case or uppercase).  The email address may contain the special characters period (.), underscore(_), hyphens (-), forward slash(\)
-	@: an @ symbol must appear after the initial characters
-	([ \da-z\.-]+: an lowercase alphanumeric character must entered. The email address may contain special characters period (.), hyphens (-), forward slash(\).
-	)\.: after second group of characters(which represents the domain) a period must appear to separate from the subdomain name.
-	([a-z\.]{2,6})$/: The email address is required to end with two or four alphanumeric value inclusive or uppercase and lowercase letters. matches when the precding characters occurs at least 2 times but not more than 6 times.
-	The brackets group com and net and separates them to indicat that they are conditional.
-	?: makes the preceding token optional. An example would be Dec(ember)?25(th), which would provide results similar to but not limited to Dec 25, and December 25th.

### OR Operator

The OR operator allows for developers to match characters or expressions on th left and right of the | (pipe character).  A developer can provide as many terms as desired, as long as they are separated by a | character. The pipe character | separates terms contained within eac group. 

### Character Classes
Character classes are interchangeable with character set.  The developer is can establish the parameter by which matches are identified.  The developer would place the character that they would like to match between square brackets. 
The matches in a character class bracket only identify a single character. The order of the character does not play a factor in the results.
-	[0-6]: represent a range of characters.  A single digit between 0 and 6 will be identified.
-	[ia]:  will identify either an data that contains either an i such as Pit or an a such as Pat.
-	[^]: the caret negates the character class, which results in the matches to characters that are not in the character class or set. (Negated Class)
-	\w : always matches  ASCII characters inclusive of digits and underscore.
-	\w: as it relates to Unicode will match letters, digits, and ideographs, as well as many other scripts
-	\d: is the shorthand form of [0-9] will identify all digits within the range
-	\s will identify any whitespace character such as space, tabs, returns and form feeds

### Flags
A flag expression can change how the expression is interpreted.  Flags are denoted as /.+/igm. A developer can disable case insensative on a whole expression by adding /i for example an expression denoted as /AEIOU/i would match aeiou. Developer can use a host of other flags such as:
- global search, which is denoted as g. the last match index is retained allowing subsequent searches to start from the end of the previous match.
- s  flag is represented by Dot(.) which matched any character including newline.
- y flag will match from it last index position and ignores the global flag if set.
- m  flag is a multiline flag, begining and end anchors, which represent the start and end of a line.  The anchors used (^ and $)
- u flags allow for developer to extend unicode escapes in the form of \x{FFFFF}.

### Grouping and Capturing
Regular expressions can be grouped together utilizing parentheses or round brackets.  However, if, a developer wishes to define a class he/she should utilize square brackets and curly braces for quantifiers with specific limits.

### Bracket Expressions
Bracket expressions match one character out of a set of characters.  The square brackets encompass syntax with a hyphen(-) to represent a range and caret(^)at the start that negates the bracket expression. the ^ should be place before the final literal or the closing to create a match. The ] has to be entered as the first character after the opening or the negating ^, to be matched.

### Greedy and Lazy Match

Greedy matches tend happen when developer utilize the,<.+> expression.  This expresssion will when paired with a string will create a continuous loop were the preceding token will sought as often as possible until failure. The * and repetition using curling braces are also fready quantifiers.

A developer can create a Lazy or reluctant quantifer by affixing a question mark after a greedy expression or quantifer, such as a + or * This provide instruction need to repeat the string the least amount of times required.

### Boundaries
The caret (^) and metacharacter(\b) will both return a match of zero-length. Since the first character matched,  the subsequent data token is advance, and the email address is allow to match and empty string and the search is determined to be successful. For example utilizing the following input:

Jack with application of a caret ^.  For our purposes will display as ^Jack.  The match will be J. Since J is the start of the string. The remaining letters are passed through tokens, since are not at the being of the string an are not required to be matched. 
Jack% with the application of a \b anchor. For our purposes will display \b jack%. The match will be Jack. Since Jack is the start of a word string and % is not a word value. However, you could receive a match if the percentage sign is change to 4, since digits are considered a word character.
the metacharacter (\b) as anchor can be applied in three positions. The \b determines the position before the first character in a string and after the last character in the string if the character is a word.  Or between two characters in the string, that contains a word character and null word character.

### Back-references
A developer that is seeking to reference a pair to opening and closing HTML tags, and the text in between can do so by backreferencing the same text as previously matched by a capturing group.  The backreference is noted by \1.  The number after / represent which capture group the developer would like to refer to and \ represents the HTML tag is being matched.  Here is an example:
<([A-Z][A-Z0-9]*)\b[^>]*>.*?</\1>

A developer utilizing the aforementioned information would be able to determine that the backreference her is [A-Z][A-Z0-(]*.

Special not a back reference cannot be utilized inside of a character class. The \1 is defined as an error or a digital value of 1.  In addition in a Repetition where a new match is found by a capturing parentheses, the previously save match is overwritten. Here is another example:
-(\w)a\1: Should be interpreted as \w Word with a case sensative 'a' where the number 1 represents the first capture group.

### Look-ahead and Look-behind
Developer commonly refers to the look-ahead and look-behind as the look-around. The look-around is a zero-length assertion.  Characters are matched, however the matches discarded, only returning match or no match.  The reason for this is that the characters in a string are not consumed, however an assertion as to whether a match is possible or not. Allows for developer to create regular expression that would be impossible to create without them.  Here are a few examples:
- \d(?=ab): represents a positive look-ahead that requires a digit between 0-9, with character matches at case sensative'a' and case sensative 'b'.
- \d(?!ab): represents a negative look-ahead that requires a digit between 0-9, where ?! specifies that if matches results are discarded, with character matches at case sensative 'a' and case sensative'b'.
-(?<!ABC): represents a negative look-behind where the group can not match before the main expression,  the matches are discarded.
-(?<=ABC): represents a positive look-behind where the group matches prior to the main expression without including results.

## Sources and References
-	[Zparacha.com]( http://zparacha.com/validate-email-address-using-javascript-regular-expression)
-	[RegExp]( https://www.regular-expressions.info/lookaround.html)
	
- [Regexr](https://regexr.com/)  

- [Webtrends](https://analytics.webtrends.help/docs/regular-expression-components)

## Author

[github]https://github.com/Patrena94
