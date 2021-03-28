
# Gawkward
#lecture #cs3377
- Awk = an _interpreted_ programming language designed to process text and is typically used as a data extraction/reporting tool
- **Interpreters** run code as it comes along as opposed to compiling and then running it (tends to be slower than compiled programs too)
  - However, many modern interpreters use JIT compiling to make things faster
- Used a lot to extract 
- Gawk is the GNU version of Awk
- Awk works on *streams*
- **Streams** are sequences of data made available over time, similar to a conveyor belt
- We will use awk in a configuration where the code resides in a file, and the data is in another file. We use the `-f` option to use (g)awk in this way:
`gawk -f <codefile> <streamfile>`

## Anatomy of an Awk Program
- Consists of a series of patterns like:

```shell
condition { action }
...
```

- Condition is usually an expression and action is a series of commands
- Awk takes the input file and splits it up into lines. The condition checks if the line matches it and executes the actions if it does
- You can leave the condition or the action blank, which will run the default thing:
  - Default condition = match every line
  - Default action = print to stdout

## Example Awk Programs
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
