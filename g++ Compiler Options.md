# `g++` Compiler Options
#wiki #cs3377 

This article concerns the `gcc` [[GNU Compiler Collection (gcc)|compiler]].

## Debugging Symbols
Using `-g`, `g++` will produce debugging information, which can be used by `gdb`

## Optimization Levels
In most situations, optimization isn't necessary anymore, but sometimes it's useful. There are multiple levels to this: `-O/-O1`, `-O2`, `-O3`, all of which add different levels of optimizations at the expense of compile time (and sometimes, binary size).

The optimizations taken may surprise you—functions/variables that don't exist, program flow that is changed, and some statements that aren't executed at all. This is why optimization should be done at the end, before releasing your code.

You can technically use `-g` with `-O`, but it doesn't really make sense to do so,

## Warnings
Warnings are useful letting you know if what you're doing is not necessarily good practice. `-W` turns on all optional warnings that are desirable for all normal code. You can specify different warnings similarly: `-W[name]`.

**It's a good idea to use `-Wall`.**
