# class 19

## <ins>*Automation*

refers to the process of generating tools that execute tasks without the help of human intervention.

__watchdog__

watchdog is a python API library that used to monitor file system events. 


__shutil__

shutil module helps you automate copying files and directories. 
This saves the steps of opening, reading, writing and closing files when there is no actual 
processing. It is a utility module which can be used to accomplish tasks, such as: 
copying, moving, or removing directory trees.

## <ins>*Regex*

Regular expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not. 

Example of applications:

- search engines
- search and replace tools

<ins> *Basic Patterns: Ordinary Characters*

Ordinary characters can be used to perform simple exact matches:

```py
import re

pattern = r"Hello"
sequence = "Hello World !"
if re.match(pattern, sequence):
    print("Match!")

```


<ins> *Wild Card Characters: Special Characters*

[abc] - Matches a or b or c.

[a-zA-Z0-9] - Matches any letter from (a to z) or (A to Z) or (0 to 9).

\w - Lowercase 'w'. Matches any single letter, digit, or underscore.

\W - Uppercase 'W'. Matches any character not part of \w (lowercase w).

\s - Lowercase 's'. Matches a single whitespace character like: space, newline, tab, return.

\S - Uppercase 'S'. Matches any character not part of \s (lowercase s).

\d - Lowercase d. Matches decimal digit 0-9.

\D - Uppercase d. Matches any character that is not a decimal digit.

\t - Lowercase t. Matches tab.

\n - Lowercase n. Matches newline.

\r - Lowercase r. Matches return.

\A - Uppercase a. Matches only at the start of the string. Works across multiple lines as well.

\Z - Uppercase z. Matches only at the end of the string.

\b - Lowercase b. Matches only the beginning or end of the word.

{x} - Repeat exactly x number of times.
{x,} - Repeat at least x times or more.
{x, y} - Repeat at least x times but no more than y times.

