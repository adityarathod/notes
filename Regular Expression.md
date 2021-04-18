# Regular Expression
#wiki #cs3377 

In [[Formal Language Theory|formal language theory]], a **regular expression** (regex) is a sequence of characters the forms a search pattern.

The best resource to learn regexes is [RegexOne](https://regexone.com).

## Metacharacters

There are many metacharacters and the full list varies by the flavor of regex used, but here are some basics:

 | Metacharacter | Description                                                          |
 | ------------- | -------------------------------------------------------------------- |
 | .             | Matches any single character                                         |
 | `[ ]`         | Matches a set of characters inside the brackets                      |
 | `[^ ]`        | Matches anything _not_ inside the brackets                           |
 | `^`           | Matches the starting position of the string                          |
 | `$`           | Matches the ending position of the string                            |
 | `( )`         | Defines a marked sub-expression (usually used to capture that value) |
 | `*`           | Matches the preceding element 0 or more times                        |
 | `+`           | Matches the preceding element 1 or more times                        |
 | `{m, n}`      | Matches the preceding element at least m and at most n times         | 