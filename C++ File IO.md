# C++ File I/O
#wiki #cs3377 

You can read up on this [online](https://www.cplusplus.com/doc/tutorial/files/). One basic thing you must `#include` is `fstream`.

## Opening Files For Reading
1. Declare a variable of type `std::ifstream`.
2. Open the file for reading using the `.open(filename, ios::in)` method.
    - The filename must be a C-style string, which can be obtained from a C++ string by using the `.c_str()` method.
3. Check if the file was opened properly by using the `.is_open()` method.
4. Close the file when done using the `.close()` method.

## Reading Data
You can read data from files using multiple method or functions.

### Getting C-Style Strings
- `istream::get(...)`
- `istream::getLine(...)`

### Getting C++-Style Strings
- `std::getLine(...)`

## Opening Files for Writing
Same as opening files for reading, but the type is `std::ofstream`.
