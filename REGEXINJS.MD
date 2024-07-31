# Intro to Regex for Web Developers

Regular expressions (regex) are a powerful tool for finding patterns in strings. As a web developer, understanding regex can help you with tasks such as validating user input, extracting data from strings, and replacing text.

## What are Regular Expressions?

Regular expressions are a way to describe a search pattern using a string of characters. They can be used to find matches in a string, and can be created using a variety of methods, including forward slashes `//` or the `new RegExp()` constructor.

## 1.

- Regular expressions find parts of a string that match a pattern and then used in methods like `match`, `test`, or `replace`
- You can define the regex beforehand, or directly when calling the method

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722398594/1_rj2r1y.png" alt="Regular expressions in javascript">
</p>

## 2.

- Match individual characters one at a time, or put multiple characters in square `brackets []` to capture any that match Capture a range of characters with a `hyphen -`

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722398993/2_ranunj.png" alt="Regular expressions in javascript">
</p>

## 3.

- Add optional flags to the end of a regex to modify how the matcher works.

- In JavaScript, these flags are:

1. `i` = case insensitive
2. `m` = multi line matching
3. `g` = global match (find all, instead of find one)

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722399186/3_byiqei.png" alt="Regular expressions in javascript">
</p>

## 4.

- Using a `caret ^` at the start means **"start of string"**
- Using a `dollar sign $` at the end means **"end of string"**
- Start putting groups of matches together to match longer strings

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722399408/4_a25imz.png" alt="Regular expressions in javascript">
</p>

## 5.

- Use wildcards and special escaped characters to match larger classes of characters

1. `.` = any character except line break
2. `\d` = digit
3. `\D` = NOT a digit
4. `\s` = white space
5. `\S` = any NON white space
6. `\n` = new line

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722399592/5_bccpmi.png" alt="Regular expressions in javascript">
</p>

## 6.

- Match only certain counts of matched characters or groups with quantifiers

1.  `.*` = zero or more
2.  `?` = 0 or 1
3.  `{3}` = exactly 3 times
4.  `{2, 4}` = two, three, or four times
5.  `{2,}` = two or more times

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722399904/6_zbleoh.png" alt="Regular expressions in javascript">
</p>

## 7.

- Use `parens ()` to capture in a group.
- `match` will return the full match plus the groups, unless you use the `g` flag
- Use the `pipe operator |` inside of `parens ()` to specify what that group matches

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722400310/7_o2vugu.png" alt="Regular expressions in javascript">
</p>

## 8.

- To match special characters, escape them with a `backslash \`

- Special characters in JS regex are: `^` `$` `\` `.` `*` `+` `?` `( )` `[ ]` `{ }` `|`

- So to match an `asterisks`, you'd use: `\*` Instead of just `*`

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722400722/8_rpboih.png" alt="Regular expressions in javascript">
</p>

## 9.

- To match anything BUT a certain character, use a `caret ^` inside of square brackets. This means `^` has two meanings, which can be confusing.

- It means both **"start of string"** when it is at the front of a regex, and **"not this character"** when used inside of square brackets.

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722400903/9_pn57nd.png" alt="Regular expressions in javascript">
</p>

## 10.

💡 Regexs can be used to find and match all sort of things, from urls to filenames

💡 HOWEVER! be careful if you try to use regexs for really complex tasks, such as parsing emails (which get really confusing, really fast), or HTML (which is not a regular language, and so can't be fully parsed by a regular expression)
