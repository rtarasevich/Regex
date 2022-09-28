# Using RegEx to Match and Validate URLs

URL Regular Expression Validator - How to Write & What it's Doing:

## Summary

Don't you just hate when you type in a website URL incorrectly and it doesn't work? Well, tough. This is why and it isn't asking too much. The developers are using this Regex to match or validate your URL and I think they make a fair point.

See below for the proper syntax for matching or validating any URL:

/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

Since every regex is considered to be a literal, so the pattern must be wrapped in forward slashes (/), which is a bit odd considering that we use back slashes (\) to break up data within the regex.

### Anchors

The ^ and $ characters are both anchors, the ^ at the beginning/left and the $ at the end/right.
The ^ anchor signifies a string that begins with the characters that follow it.
The $ anchor signifies a string that ends with the characters that precede it.

Long story short, so far, you're gonna see every regex start with /^ and end with $/

### Quantifiers

These can be broken up into 4 chunks:

a. (https?:\/\/)?
b. ([\da-z\.-]+)
c. ([a-z\.]{2,6})
d. ([\/\w \.-]*)*

a. The ? means that whatever precedes said ? will match the pattern 0 times or 1 time, but not multiple times. The first ? is saying "Yea, there can be an http or an https or neither, it's all good, I'll still know what's up. But if you screw around and throw in an extra h or t or think there should be a q or a u, I'm kicking it back to you to try again." The second ? applies to the entire sub-expression, meaning the https, the :, and the forward slashes. Same deal as before though, you can be an overachiever and type in https://www. or you can just skip everything before the www. Heck, you don't even need the www. It's all gravy.

b. The + means that whatever precedes said + (but within those parentheses - more on those later) will match the pattern 1 or more times. And the letter d, in this case, stands for digit, so 0-9. Thus, this little guy is saying that you can have as many digits, lowercase (this is important) letters, periods (.), or hyphens(-) in this section. Think of it as everything before the ".com" - it could be a1.com or grant-is-awesome-at-coding.123.abc.com

c. The [] will be explained in the bracket expressions section, but the {}, with 2,6 within them, are saying that whatever is in this part of the URL must match the pattern a minimum of 2 times to a maximum of 6 times, so .com, .org, .net would all work.

d. The * symbol means that whatever precedes it matches the pattern 0 or more times. The first one is saying that forward slashes (/), any alphanumeric character (w), a period (.), or a hyphen (-) is gucci. The second is saying that you can have as many of these groupings as you want, so a1.net/grant/is.awesome.at.coding/123/abc would work, if it existed, which it totally should.

### OR Operator

We don't have any of these | characters up in this regex, but if we did, we might throw one in between the d and the a-z in da-z, like so...d|a-z would mean it could contain a digit OR a lowercase letter.

### Character Classes

This is where we start saying things like meta characters. No, not like facebook. 
The \d, which we mentioned earlier in example b up above, is a meta character that matches any digit from 0-9.
The \w is anything alphanumeric, so a-z, A-Z (yes, uppercase is allowed now), 0-9, and even an underscore (_) apparently.

### Grouping and Capturing

This is where the () comes into play. Anything within the () is known as a sub-expression and is used to group sections together - you'll notice all 4 of the above examples are grouped in parentheses.

### Bracket Expressions

The [] is a bracket expression and anything inside of it represents a range of characters that we want to match. They can also be called a "positive character group," because they outline the characters we want to include. So think of example b [\da-z\.-]...we want to include digits, lowercase letters, periods, and hyphens.

The [] is a special character

### Greedy and Lazy Match


## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
