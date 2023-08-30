# Regex Tutorial: HTML tag 

by christian guzman 

this tutorial will help explain HTML elements are use and how they are structure and what each /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/ 
of these tags mean. there are various tags that are use and should consider while coding in HTML. 

# Summary

A Regular Expressions or a regex is a sequence of characters can be a search pattern. regex can be more powerful and flexible for cleansing text-based data. HTML are made up of strings and the use of regular expressoins can help match different strings. 

the regex we will analyze today is /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/ 

the below content will explain what each section of the code does.

# Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#OR-Operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)

# Regex Components 

### Anchors 

Anchors are used in regular expressions to check the first and last symbols of a string. there are two anchors you can use.
The ^ anchor matches a position at the beginning of an input string, whereas $ anchors match positions at the end of an input string.

example if you use (^) that can check if the story start with "In a galaxy far far away".
```
you user /^In a galaxy far far away/ this checks if any string starts with 'In a galaxy far far away'.
```
if you wanted to check if it ended with 'the end'. 
```
/The end$/ this check to see if the strongs ends with 'The end'
```
but if we added both of them together to make the 3rd anchor it has to match the given criteria otherwise it wont pass 
for example if the regex we enter is 
```
/^galaxy far far away&/
```
this would match all strings that have ' galaxy far far away& ' 
but will not match anything that doent match it like 
```
"in a galaxy that is far far away" 
```

### Quantifiers

we can also add quantifier to our regular expression so that it only matches certain number or characters. for example if i want my regex to be (*), or the Plus(+), and lastly (?).
```
the * matches zeros or more repetitions 

the + matches one or more repetions of the preceding character

the ? matches zeros or one instance making it optional 
```
the ? quantifiers is know as an lazy operator as it will only look for preceding characters. 
while the + and * are know as greedy operators and match the preceding character it can before stopping.
### OR Operator

OR Operator | is use to look for one thing 
```
if we were to use it it be use like so 
/there|thier/ it will look for either there or thier but it will also look for both of them
```
### Character Classes

in regex we can use 3 character classes one of these are (.) this looks for internal content in html tags, another one is /s looks for all self closeing tags. and the last one we can use is \/ which looks for not only closing tags but also end self closing tags.
for example 
```
(.*) looks for any characters in html 
\s+\/> looks for characters followed by / and then looks for a > characters 
<\/ this ends up looking for any < characters following by a / characters 
```
### Flags

Flags are modifiers for the output of a regular expression. they are also appened to the outside of the regex most are written like /regex/. 
some of the most common flags that are use is i, which the regex insensitive,and m which cause anchor characters to work for each line
for exmaple 
```
if we used i it be used like so 
/away/i  this matches tge first 'away' in any string now matter how its spell ex: 'Away', 'aWay', 'AWAY', 'aWAY'

if we used m it would be use like
/^away/m which will look at the first away that starts a line 
```
### Grouping and Capturing

In regex you are able to use () to create grouping. groups can be very useful when conjunction to expand or limit context. 
there are two types of groups capturing and non capturing. By capturing you are indicating that your interested and not only matching. 
capturing group uses () while non-capturing does not (?:)
for example:
```
([a-z]+) first it looks for one or more characters for a-z, and for making this we can go back later on if we want to repeat this 
([^<]+)* the () will capture [^<]+ the * will be used for the whole group 
```
### Bracket Expressions

the bracket expressions [] can be used to specify groups of characters to match.
```
[abc] this will match either a, b ,or c in sequence
[a-z0-9] this will match either a though z characters, and digits 0 though 9. 
```
in regex to match one or more characters we would do something like this 
```
[a-zA-Z]+ this will match one or more letters from A through Z or lowercase letter.
```
### Author 
i am a software developer
my GitHub is vortexwarrior