# Library
#wiki #cs3377 

A **library** is a file that exists on the file system that satisfies the following conditions:

- Has a specifically formatted file name
- Usually located in "known locations" but can be anywhere
- Depending on the type of library, the compiler may be used to create them
- They function similar to a tar/zip file in which multiple object files are inside the library
- Primarily used by the linker

# Linker
#wiki #cs3377 
Within a compiler toolchain, a linker is a program that uses libraries to resolve all functions into code.

The linker searches libraries (similar to how header files are used by the preprocessor) to locate every function.

In the GCC toolchain, the `-L` option directs the linker to look in specific library files. Also, the `-l` tells the linker the name of the library.


# nm command
`nm` is a command to list symbols from object files.