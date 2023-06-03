# Making An Email Formated RegEx

Nowadays it's important to have an email as when signing up for most websites or sites it is a primary piece of data allowing the user to uniquely access their account while also providing the site with a way to verify if the account holder is both real and correctly identified. This is why it's important that when jotting down the email you use, you must have a RegEx to verify the email at the very least in correct format

## Summary


The RegEx below is the one we will be covering today. It is again an email formatted RegEx. It just validates the format of the email in order to mitigate any potential mistakes. The first group which is our handle asks for 1 or more characters that can be lowercase alphabets, numbers, and the characters ('_', '.', '-'). Between the first 2 groups there needs to be an '@'. The second group looking for email service (yahoo, gmail, etc.)asks for pretty much the same as the first group excluding the underscore '_'. In between the second and third group there needs to be a period '.'. The final group will only match if the string is in the 2-6 range of characters and can only be composed of lowercase alphabets and periods '.'

The Email Regex  =  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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
Anchors instead of talking about matching characters, they instead will reveal something about string or matching process. The major thing it allows is for us to have location in a RegEx especially the beginning and the end.

Inside the RegEx the '^' character denotes the beginning of of the expression, while the '$' denotes the end of the expression.

### Quantifiers
Quantifiers specify how many times a character, group, or character class must be present in the input for a match to be accepted. There are 2 types of qualifiers, greedy and lazy. Qualifiers are naturally greed meaning they will try to match as many occurences of a pattern as possible while lazy will match as few as possible. To denote a lazy qualifier, need to add a '?' question mark after the initial qualifier

Inside the email RegEx we have 3 qualifiers as shown below

1. ([a-z0-9_\.-]+) - The '+' tells us to match we need one or more of the characters included in the bracket expression

2. ([\da-z\.-]+) - The '+' says the same as the example above

3. ([a-z\.]{2,6}) - The '{2,6}' says that this group's match needs between 2 to 6 characters (matching whatever the expression inside the backet expression requires)


### Grouping Constructs
Grouping Constructs allow developers to seperate what they are trying to match in RegEx. They are denoted by wraping the section in '()' parentheses. Below I'll show the 3 times grouping constructs were used.

1. ([a-z0-9_\.-]) - This will try to match anything that has any lowercase letter in the alphabet, numbers between 0-9 &/or the characters '_', '.', and '-'

2. ([\da-z\.-]) - This will try to match anything with numbers in it, any lowercase alphabets, &/or the characters  '.', and  '-'

3. ([a-z\.]) - This will match anything with lowercase letters and/or the characters '\', or  '.'

Each of these can searching for different phrases to match to and it's only possible because we wrapped each group with grouping constructs


### Bracket Expressions
Bracket expressions are used to denote what characters we are trying to match. We can make a range of alphabets and numbers and also include special characters if we want as well. Below I will explain the 3 bracket expressions in our email RegEx

1. [a-z0-9_\.-] - This will try to match anything that has any lowercase letter in the alphabet, numbers between 0-9 &/or the characters '_', '.', and '-'

2. [\da-z\.-] - This will try to match anything with numbers in it, any lowercase alphabets, &/or the characters  '.', and  '-'

3. [a-z\.] - This will match anything with lowercase letters and/or the characters '\', or  '.'



### Character Classes
Character Classes allow developers to write RegEx in more compact ways. Inside our email RegEx there is one character class

Within the Bracket Expression [\da-z\.-] we have '\d' which is a character class that denotes any numbers. It's the same as out the '0-9' inside the other bracket [a-z0-9_\.-]

### The OR Operator
The OR operator is a RegEx tool designed to implement a logical 'or' operation. It is normally denoted with '|'

In our RegEx above we don't have any Or Operators to show

### Flags
Flags are  optional parameters in a RegEx that allows developers to modify the RegEx's behavior of searching. They are placed at the end of the regex

There are no Flags inside our email RegEx

### Character Escapes
Character Escapes are used to denote characters that we want to match but might not register as matching characters like '{}' curly brackets or even '.' which are qualifiers. We generally  denote with '\' back slashes

In our regex we have this happen 3 times (each on the same character). In the regex 2 times in bracket expressions and once in between them we have '\.' This says that we want to recognize the period as a character we are also matching

## Author

A young junior full stack development student learning the ropes of the industry / technology

Github Profile - https://github.com/QDatcher
