# Include Paths
#wiki #cs3377 

_This focuses on the behavior of the [[GNU Compiler Collection (gcc)|GNU Compiler Collection]]_.

## The Two Types of Include
The preprocessor does one of two things when it encounters `#include`.

### Angle Brackets
When you do something like `#include <iostream>`, you are telling the preprocessor to search in an implementation-dependent manner (directories chosen by the preprocessor).

You can specify that you have other header files you want to include in this way in GCC by using the `-I <path>` option.

Note that this directive is *not* recursive, so you must reference it in your code with the proper folder structure. Shell expansions such as `*` will not work either.

> **Note**: When specifying paths, it's a bad idea to use `~` since that's a shell expansion. Build tools will *not* understand this, so get used to typing out full paths instead.

### Quotes
When you do something like `#include "myheader.h"`, you're telling the preprocessor to search in the same directory containing the directive.
