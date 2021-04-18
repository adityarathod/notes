# Pipe Streams in C
#wiki #cs3377 

**Pipe streams** are a method to pipe to and from a process, which allows for C/C++ programs to run shell commands. 

The C functions to perform this are `popen()` and `pclose()`, which return a pointer to a `FILE` struct. As such, they operate very similar to `fopen()` and `fclose()`.

[Manual page](https://man7.org/linux/man-pages/man3/popen.3.html)