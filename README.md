# bin-ripper
Often, fuzzing a binary-only target is hard to setup and hard to monitor. There are many fuzzers out there that have been developed for binary-only targeting, but which ones do you use? `bin-ripper` attempts to answer that question while solving the first problem with a python interface.

## Overview of Needs

### Multi-Arch Support
It needs to be pretty easy to use this on ARM, Mips, and x86.

### Post-Mutation Operations
It's pretty common that you need to do something after fuzzing once, like reseting the virtual disk or object where the file is running. There is some work on this:
- [AFL++ Custom Mutators](https://github.com/AFLplusplus/AFLplusplus/blob/stable/docs/custom_mutators.md)
- [Base AFL Post Library](https://github.com/google/AFL/tree/master/experimental/post_library)

Either way, we need a fast way to do an operation after we do a mutation. 
