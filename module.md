---
title: modules
date: 2023-03-28
---

The module command works by modifying your environment (mostly the PATH and LDLIBRARYPATH variables).

There’s a description at [https://doku.lrz.de/display/PUBLIC/Environment+Modules](https://doku.lrz.de/display/PUBLIC/Environment+Modules).

- `module avail` tells you what modules are available.

- `module list` tells you which modules you are currently using.

- `module load intel` loads the default version of the Intel module.

- `module load intel/17.0` loads version 17.0 of the Intel compiler suite.

- `module unload intel` unloads the Intel version in use.


## Example 

To set persistent module loading when login, add to ~/.profile something like this

```
 module load intel/19.0
 module load mpi.intel/2019
 module load amplifier_xe/2019
 module load inspector_xe/2019
 module load advisor_xe/2019
 module list
```

where you can load whatever you prefer. 

The modules ending with _xe/2019 are the profilers (optional). 

To compile parallel programs using intel compilers (recommended) you need the first two.

