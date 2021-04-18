# GNU Awk
#wiki #cs3377

Awk is an _interpreted_ programming language designed to process text and is typically used as a data extraction/reporting tool. GNU Awk (or `gawk`) is the GNU rewrite of this program.

> **Note on interpreters**
> **Interpreters** run code as it comes along as opposed to compiling and then running it. They generally tend to be slower than compiled programs; many modern interpreters use JIT compiling to make things faster.

Awk operates on _streams_ of lines, and can get its input from a pipe, input redirection, or a file.

> **Note on streams** 
> **Streams** are sequences of data made available over time, similar to a conveyor belt.

## Writing Awk Programs
Programs written in Awk are series of patterns in this format:

```shell
condition { action }
...
```

A **condition** is usually a matching expression and an **action** is a series of commands. Since Awk operates on lines, the condition checks if the line matches the specified pattern and executes the specified action if it does.

Either the condition or the action can be blank, which makes Awk fall back to its default behaviors:
- Default condition = match every line
- Default action = print to stdout

## Running Awk Programs

Awk programs can be written on the fly inside a string, or can reside in a file. To specify which program to run, we use the `-f` option with a code file:

```shell
gawk -f <codefile>
```

We can also specify a file to process:

```shell
gawk -f <codefile> <streamfile>
```

## Examples
Print the whole line, line by line

```shell
{ print $0 }
```

Print the first word in the entire line, line by line

```shell
{ print $1 }
```

Print lines more than 20 characters long:

```shell
length($0) > 20
```

Print the first word of lines more than 20 characters long:

```shell
length($0) > 20 { print $1 }
```

Perform actions before and after a stream is processed (using the `BEGIN` and `END` directives):

```shell
BEGIN { myCount = 0; printf "Beginning to count lines longer than 20.\n"; }
length($0) > 20 { print $0; myCount += 1; }
END { printf "Final count was %d\n", myCount; }
```
