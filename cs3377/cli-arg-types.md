# Command Line Argument Types
#wiki #cs3377 

## Flags
Arguments that either exist or don't exist. In [[tclap]], this is called a `SwitchArg`.

### Example
```bash
g++ -v
```
 
In this case, `-v` displays the version.

## Value Arguments
Arguments that take a value along with the argument. In [[tclap]], this is called a `ValueArg`.

### Example
```bash
g++ -o program2 [...]
```
 
In this case, `-o` specifies the output file name.

## Unlabeled Arguments
Arguments that take a value but have no flag associated with them. In [[tclap]], this is called a `UnlabeledValueArg`.

### Example
```bash
g++ program2.cc
```

In this case, `program2.cc` is the path to a file to compile.

[//begin]: # "Autogenerated link references for markdown compatibility"
[tclap]: tclap.md "Templatized C++ Command Line Parser (TCLAP)"
[tclap]: tclap.md "Templatized C++ Command Line Parser (TCLAP)"
[tclap]: tclap.md "Templatized C++ Command Line Parser (TCLAP)"
[//end]: # "Autogenerated link references"