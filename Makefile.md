# Makefile

A control file used by [[Make]] that helps it find all the code that has been modified, re-compile things that are out of date, and re-link targets. It also maintains all the compiler flags and environments. It is, by convention, titled `Makefile` but you can name it other things (not recommended).

## Syntax
The generalized syntax for Makefiles is as follows:

```makefile
<target>: [<dependency>]*
[<TAB><command><endl>]+
```

\* = 0 or more, \+ = 1 or more

### Example
```makefile
myClass.o: myFile.h myFile.cc
  g++ -c myFile.cc
```

## Testing
You can use [[Touch]] to test these (by making targets out of date).
