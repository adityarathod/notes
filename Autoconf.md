# Autoconf
#wiki #cs3377

Autoconf is a package of [[GNU M4]] macros that produces shell scripts to automatically configure (not build) software code packages, allowing for those packages to be installed on many UNIX-like systems without manual user intervention.

Most Linux/UNIX software is packaged using Autoconf. It is a useful skill to know because of its ubiquity.

## What needs adapting across systems?
Not all UNIX-based systems are the same. Autoconf provides utilities to detect compilers, check for the presence of header files and required libraries, perform custom tests, and ensure full compatibility for a software package.

## Configuration process
Autoconf does the following:
1. Creates a `.configuration` shell script
2. Executes the script on your UNIX-based OS
3. Generates a [[Makefile]] that's specific to the build and your UNIX system
4. Runs other toolchains that may rely on it