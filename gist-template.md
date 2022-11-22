# Title (replace with your title) 

This gist is my tutorial on the regex matching email. The regex string for this can be lengthy or short depending on the language you use. This string will find an email within the document. It basically checks to see if a string matches the basic requirements to be an email address. This tutorail is meant for beginners.
For a quick reference, see the MDN JavaScript Guide's Regular Expressions Cheatsheet

## Summary

Basically a regex of an email would be composed of an object that states that an lowercase letters between and z can be used, then any of the uppercase letters between a and z can be used. Then it says any numbers between 0 and 9 can be there. then it adds in the special characters that emials allow. Next it does the @ symbol that all emails have. Then it again takes in all the upper and lowercase letters and numbers for all of the different domains. Last it adds all the lower and uppercase letters and numbers for the .com or, org, or any of the other endings there are for emails. This is essentially the formula for checking documents for an email address. Simply put, Michelle@gmail.com would be picked up by making sure we cover all of the possibilities. 
An example would be: ^[a-zA-Z0-9]+(?:\.[a-zA-Z0-9]+)*@[a-zA-Z0-9]+(?:\.[a-zA-Z0-9]+)*$

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

Our anchors mark the start and end to our regex. This tells javascript that this is where our string is and to check for everything inbetween. In our example we see that the carrot '^'and the dollar sign '$' do just this. ^[a-zA-Z0-9]+(?:\.[a-zA-Z0-9]+)*@[a-zA-Z0-9]+(?:\.[a-zA-Z0-9]+)*$

### Quantifiers 

These are used to tell how many instances the component can or should be matched.

The shorthand is:

zero or more: *
zero or one: ?
one or more: +
exactly one: (indicated by the absence of a quantifier)

By using curly braces:

a minimum of n, and a max of m: {n,m}
a minimum of n, and no maximum: {n,}
no minimum, and maximum of m: {,m}
exactly n: {n}

In our email regex, ony one type of quantifier is used. The shorthand quantifier + is used twice.

Shorthand quantifier (first instance)

The plus sign quantifier + is used to indicate that matches to the character class [a-z0-9_\.-] should be one or more characters in length.

Curly braces quantifier

The curly brace quantifier {2,6} is used to indicate that matches to the character class [a-z\.] must be a minimum of two and a maximum of six characters in length. Our example doesn't use this but other regex strings can.

### Grouping Constructs

Parentheses () are used to create grouping constructs (sometimes called "capturing groups" or "subexpressions") within our regular expressions. Grouping constructs can then be specified and quantified independently from other components of our regular expression.

The first grouping construct comprises the character class [a-z0-9_\.-] and the quantifier +. It corresponds to the username or "local-part" of the email address.

The second grouping construct comprises the character class [\da-z\.-] and the quantifier +. It corresponds to the mailserver name of the email address.

The third grouping construct comprises the character class ([a-z\.]{2,6}) and the quantifier {2,6}. It corresponds to the top-level domain or "TLD" of the email address. Our example doesn't have this, but it does get used.

### Bracket Expressions

Square brackets [] are used to create bracket expressions in regexes. This allow us to specify a group of characters that we want to match in a regular expression. They let us specify an "ad hoc" character class comprising any set of individual characters (e.g. _), character classes (e.g. \d), and/or character ranges (e.g. [a-c]) that we want to match.

Our email regex has four bracket expressions: [a-zA-Z0-9], [a-zA-Z0-9],[a-zA-Z0-9], and [a-z\.].

The first bracket expression [a-z0-9_\.-] specifies which characters the username or "local-part" of an email address will match in our regular expression.

The second bracket expression [a-zA-Z0-9] specifies which characters the mailersever name of an email address will match in our regular expression.

The third bracket expression [a-z\.] specifies which characters the top-level domain (or "TLD") of an email address will match in our regular expression.

### Character Classes

Character classes are sets of characters we want to match in our regex's, such as numbers, lowercase letters, uppercase letters, and alphanumeric characters.

In JS, character classes can be indicated by bracket expressions, and metacharacters.

examples of bracket expressions are:[a-z] [A-Z] [0-9]

examples of metacharacters are: \d [0-9] [A-Za-z0-9_]

. a wildcard that matches any character that is NOT a line terminator (e.g. \n)

### The OR Operator



### Flags

Flags are used in JavaScript regexes to add additional functionality to matching behavior, they are placed after the closing / of the regular expression, the i after the second / in /[a-z]/i

Some flags are

 [i] ignore case flag: match lowercase and uppercase letters, even if they aren't explicitly specified in the regex character classes (also called case-insensitive).

[g] global flag: match all instances of the regex pattern in an input string, not just the first one.

### Character Escapes

Character escapes allow us to treat characters that have special meanings in JavaScript as "literals" or the actual character we see on our screen.

Normally the dot [.] is a metacharacter that functions as a wildcard and matches any character other than a line terminator, so [.] would match any letter, any number, and any symbol:

. match Z
. match %
. match {
. match 5
. match (a space)

## Author

I am a junior developer, I hope to gain more knowledge on regex, and many other topics in my future!
git https://github.com/mfarrell23/regEx.git

