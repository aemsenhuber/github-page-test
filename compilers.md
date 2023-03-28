---
title: compilers
date: 2023-03-28
---

compilers
---

To compile use ```icpc``` or ```mpiicpc```.

Fast options are (last two are optional because they could slow down the compilation)

```-O3 -xHost -unroll -g -ip -ipo```

debug are

``` -O0 -check all -warn all -fpe0 -u -traceback -init=snan,zero,array```

profiling are (same comment as fast)

``` -O3 -xHost -unroll -g -pg -ip -ipo```

Alternatively you can use the default gnu compiler mpif90, but you have to

```
 module unload intel/19.0
 module unload mpi.intel/2019
```
