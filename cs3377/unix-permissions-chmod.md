# UNIX Permissions and `chmod`
#wiki #cs3377 


## Changing Permissions
This is done via `chmod`, which changes the file mode bits using either a symbolic representation or an octal pattern

There are three types of permissions that can be given to groups:
- Read (`r`)
- Write (`w`)
- Execute (`x`)

### Symbolic Representation
- The groups available for usage:
  - User `u`
  - Owner group `g`
  - Others `o`
  - All users `a`

**Example**: `chmod u+x myfile`

### Octal Notation
This is more commonly used. We have triplets for each of `u`, `g`, and `o`.

#### Example
Set `rwxr-xr--` on `myfile`.

Triplet for `u`: `rwx` = 4 + 2 + 1 = 7
Triplet for `g`: `r-x` = 4 + 0 + 1 = 5
Triplet for `o`: `r--` = 4 + 0 + 0 = 4

Result: `754`
Usage: `chmod 754 myfile`
