# NASA Principle
#wiki #cs3377 

This states:

> ***Test what you fly, fly what you test.***

In essence, if you don't test the exact thing you launch, you don't fully understand its behavior. **This includes things like removing things like [[gplusplus-compiler-options]]!**

## Things To Consider
- Do you ship code with debugging symbols?
- Do you have debug/release configurations?
- Do you enable/disable debugging macros in the preprocessor?
- Do you allow compiler optimizations?

If so, you must test the release version too before passing it to your users.

[//begin]: # "Autogenerated link references for markdown compatibility"
[gplusplus-compiler-options]: gplusplus-compiler-options.md "g++ Compiler Options"
[//end]: # "Autogenerated link references"