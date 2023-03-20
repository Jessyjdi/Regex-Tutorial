# RegEx Tutorial

<span style="color: Orange">RegEx</span> stands for regular expression. A regular expression is used to identify patterns in strings. Regular expressions consist of a series of characters that represent a search pattern. Regular expressions are used in search engines, in search and replace dialogs of word processors and text editors, in text processing utilities such as sed and AWK, and in lexical analysis. Regular expressions are supported in many programming languages.

## Summary

In this computer era the Regex (Regular Expression) is used almost on day to day basis. Understanding how it works is very important. We use passowrd to access any application either it can be on your mobile or desktop/laptop the user has to sign-in to proceed further. 

<span style="color: Orange">/^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[^a-zA-Z0-9])(?!.*\s).{8,20}$/</span>

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

<span style="color: Orange">Anchors</span> belongs to a family of RegEx. They are used to assert the engines to search for the text. 

- The caret ^ matches at the begining of the string / text.

- The dollar $ matches at the end of the string / text. 

<span style="color: Orange">/^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[^a-zA-Z0-9])(?!.*\s).{8,20}$/</span>

Both anchors together are often used to test whether or not the string fully matches the above pattern.


### Quantifiers

<span style="color: Orange">Quantifiers </span>specify how many instances of a character, group, or character class must be present in the input for a match to be found. Qualtifiers can be either greedy or lazy(non-greedy).

<table>
    <thead>
      <tr>
        <th>Greedy Quantifier</th>
        <th>Lazy Quantifiers</th>
        <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>*</td>
            <td>* ?</td>
            <td>Matches zero or more times.</td>
        </tr>
        <tr>
            <td>+</td>
            <td>+ ?</td>
            <td>Matches one or more times.</td>
         </tr>
          <tr>
            <td>?</td>
            <td>? ?</td>
            <td>Matches zero or one time.</td>
         </tr>
          <tr>
            <td>{ n }</td>
            <td>{ n }?</td>
            <td>Matches exactly n times.</td>
         </tr>
          <tr>
            <td>{ n ,}</td>
            <td>{ n ,}?</td>
            <td>Matches at least n times.</td>
         </tr>
          <tr>
            <td>{ n , m }</td>
            <td>{ n , m }?</td>
            <td>Matches from n to m times.</td>
         </tr>
    </tbody>
  </table>

  The password that has at least 
 - One lowercase letter <span style="color: Orange">(?=.*[a-z])</span>,
 - One uppercase letter <span style="color: Orange">(?=.*[A-Z])</span>, 
 - One digit <span style="color: Orange">(?=.*[0-9])</span>, 
 - One special character <span style="color: Orange">(?=.*[^A-Za-z0-9])</span>,
 - Must be 8 to 20 characters long <span style="color: Orange">(?=.{8,20})</span> .
 - No white space <span style="color: Orange">(?!.*\s)</span>

### Grouping Constructs

A part of a pattern can be enclosed in parentheses (...). This is called a <span style="color: Orange"> “capturing group” or "grouping constructs"</span>. The Regex must satisfy the following conditions of the groups:

<table>
    <thead>
      <tr>
        <th>Grouping</th>
        <th>Effect</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>(?:...)</td>
            <td>Match everything enclosed</td>
        </tr>
        <tr>
            <td>(...)</td>
            <td>Capture everything enclosed</td>
        </tr>
    </tbody>
  </table>

(?=.*\d) (?=.*[a-z]) (?=.*[A-Z]) (?=.*[^a-zA-Z0-9])  (?!.*\s) 

Thea above conditions are validated using https://regex101.com/

 #### <span style="color: yellow">Positive Lookahead</span>

- (?=.*[A-Z]) A-Z matches a single character in the range between A (index 65) and Z (index 90) (case sensitive)
- (?=.*[a-z]) a-z matches a single character in the range between a (index 97) and z (index 122) (case sensitive)
- (?=.*[^a-zA-Z0-9]) Match a single character not present in the list below [^a-zA-Z0-9]
a-z matches a single character in the range between a (index 97) and z (index 122) (case sensitive)
A-Z matches a single character in the range between A (index 65) and Z (index 90) (case sensitive)
0-9 matches a single character in the range between 0 (index 48) and 9 (index 57) (case sensitive)

 #### <span style="color: yellow">Negative Lookahead</span>

- (?!.*\s) \s matches any whitespace character (equivalent to [\r\n\t\f\v \u00a0\u1680\u2000-\u200a\u2028\u2029\u202f\u205f\u3000\ufeff])
. matches any character (except for line terminators)
{8,20} matches the previous token between 8 and 20 times, as many times as possible, giving back as needed (greedy)

### Bracket Expressions

<span style="color: Orange">Bracket Expression</span> are enclosed in square brackets. The [a-z], [A-Z] and [^a-zA-Z0-9] according to these atleast one character must match the expressions.

### Character Classes

<span style="color: Orange">Character class</span> will match one out of several characters.

<table>
    <thead>
      <tr>
        <th>Characters</th>
        <th>Meaning</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>[abc]</td>
            <td>A single character of a, b or c</td>
        </tr>
        <tr>
            <td>[^abc]</td>
            <td>A character except: a, b or c</td>
        </tr>
        <tr>
            <td>[a-z]</td>
            <td>A character in the range: a-z</td>
        </tr>
        <tr>
            <td>[^a-z]</td>
            <td>A character not in the range: a-z</td>
        </tr>
        <tr>
            <td>[a-zA-Z]</td>
            <td>A character in the range: a-z or A-Z</td>
        </tr>
        <tr>
            <td>/d</td>
            <td>digit [0-9]</td>
        </tr>
         <tr>
            <td>/b</td>
            <td>word boundary</td>
        </tr>
         <tr>
            <td>/s</td>
            <td>white space</td>
        </tr>
    </tbody>
  </table>


### The OR Operator

 <span style="color: Orange">OR operator ( | )</span>  can be used if we want to match the regex based on one condition. If we want to match a combonation or if maybe more than one type of input, the OR operator is very helpful.

The regex <span style="color: Orange"> /^ I choose (strong|week) password$/</span> will accept either I choose strong password OR I choose week password.

The explicit OR operator isn't used in our password expression, but it's a very useful tool in regex.

### Flags

<span style="color: Orange">Flags</span> will always follow the closing forward slash of an expression, and change how it is interpreted. There are no flags in this example; however, the following are some popular flags.

<table>
    <thead>
      <tr>
        <th>Flag</th>
        <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>d</td>
            <td>Generate indices for substring matches</td>
        </tr>
        <tr>
            <td>g</td>
            <td>Global search</td>
        </tr>
        <tr>
            <td>i</td>
            <td>A character in the range: a-z Case-insensitive search</td>
        </tr>
        <tr>
            <td>m</td>
            <td>Multi-line search</td>
        </tr>
        <tr>
            <td>s</td>
            <td>Allows . to match newline characters</td>
        </tr>
        <tr>
            <td>u</td>
            <td>"unicode"; treat a pattern as a sequence of unicode code points</td>
        </tr>
         <tr>
            <td>y</td>
            <td>Perform a "sticky" search that matches starting at the current position in the target string</td>
        </tr>
    </tbody>
  </table>


### Character Escapes

The following character escapes are used in the RegEx.

<table>
    <thead>
      <tr>
        <th>Symbol</th>
        <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>^</td>
            <td>The Caret</td>
        </tr>
        <tr>
            <td>$</td>
            <td>The Dollar sign</td>
        </tr>
        <tr>
            <td>.</td>
            <td>The period or dot</td>
        </tr>
        <tr>
            <td>?</td>
            <td>The Question mark</td>
        </tr>
        <tr>
            <td>*</td>
            <td>An asterisk</td>
        </tr>
        <tr>
            <td>\</td>
            <td>The backslash</td>
        </tr>
         <tr>
            <td>( and )</td>
            <td>The opening and closing parenthesis</td>
        </tr>
        <tr>
            <td>[ ]</td>
            <td>The opening and closing square bracket</td>
        </tr>
        <tr>
            <td>{ }</td>
            <td>The opening and closing curly braces</td>
        </tr>
    </tbody>
  </table>


## Author

I write this tutorial while I am taking a Coding Boot Camp for full stack web developer. Please find my information below:

GitHub : https://github.com/Jessyjdi/Regex-Tutorial

Gist GitHub: https://gist.github.com/Jessyjdi/07ae20e50b05711130023e5efea88a01
