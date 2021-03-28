# Templatized C++ Command Line Parser (TCLAP)
#wiki #cs3377 

TCLAP is a C++ library to parse [[Command Line Argument Types|command line arguments]].

## Downloading
TCLAP is available from its [SourceForge page](http://tclap.sourceforge.net/). You must use proper [[Include Paths|include paths]] for the library to work.

## Usage
All of TCLAP's functionality is under the `TCLAP` namespace. As such, `CmdLine` would be `TCLAP::CmdLine`.

### Initializing a CmdLine Object
The `CmdLine` is the central object used to parse and add options. Its constructor takes three arguments:

| Type          | Description                                                                   |
| ------------- | ----------------------------------------------------------------------------- |
| `std::string` | a message to print at the bottom of the usage statement (viewable using `-h`) |
| `char`        | the delimiter separating options (should be ' ' in most cases)                |
| `std::string` | the version number of your code                                               |

#### Example
```cpp
TCLAP::CmdLine cmd("CS3377 Prog2", ' ', "1.0");
```

### Adding Flags
**Boolean flags** require a variable of type `SwitchArg`, with arguments:

| Type             | Description                          |
| ---------------- | ------------------------------------ |
| `std::string`    | single character of flag             |
| `std::string`    | long format of flag                  |
| `std::string`    | text description of flag (for usage) |
| `TCLAP::CmdLine` | `TCLAP::CmdLine` object              |
| `bool`           | default value of flag                | 
 
**Flags with required additional values** require a variable of type `ValueArg<T>`, with arguments:

| Type          | Description                                  |
| ------------- | -------------------------------------------- |
| `std::string` | single character of flag                     |
| `std::string` | long format of flag                          |
| `std::string` | text description of flag (for usage)         |
| `bool`        | whether or not the flag is required          |
| `T`           | default value of the flag if not provided    |
| `std::string` | description of the expected type (for usage) |

For more on these types of flags, read [[Command Line Argument Types|Command Line Argument Types]].
 
### Arguments Without Flags
**Arguments without a flag** require a variable of type `UnlabledValueArg<T>` with arguments:

| Type          | Description                                   |
| ------------- | --------------------------------------------- |
| `std::string` | name of the parameter (mostly unused)         |
| `std::string` | text description of argument (for usage)      |
| `bool`        | whether or not the argument is required       |
| `T`           | default value of the argument if not provided |
| `std::string` | description of the expected type (for usage)  |
| `bool`        | whether or not you can ignore the parameter   |

### Registering Arguments
All arguments (except boolean flags) need registration with the initial `CmdLine` object. This is done using the `.add(arg)` method on that object.

#### Example
```cpp
TCLAP::CMDLine cmd = /* initialize it */;
TCLAP::ValueArg<T> infile = /* initialize it */;
TCLAP::ValueArg<T> outfile = /* initialize it */;
cmd.add(outfile);
cmd.add(infile);
```

Pretty self-explanatory.

### Parse Arguments
Once all arguments have been register, we must start the parsing by providing TCLAP with the `argc`/`argv` options that were passed via `main()`.

This can be done using the `.parse(argc, argv)` method on the `CmdLine` object.

If the parse occurs successfully, then the call with return. Otherwise, the usage will be printed to the screen and the program will exit.

### Retrieving Parsed Arguments
Once the arguments have been parsed, we can query for the argument using the argument objects' `.getValue()` method.

### Getting Usage Manually
Since TCLAP does not validate things like the content of arguments nor mutually-exclusive arguments, you may find it useful to print an error message and the correct usage. You can get the usage string by using the `.getOutput()->usage(cmd)` method, like so:

```cpp
TCLAP::CMDLine cmd = /* initialize it */;
cmd.getOutput()->usage(cmd);
```
