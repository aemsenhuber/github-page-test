---
title: modules
date: 2023-03-28
---

modules
---

As for many clusters, get available modules by typing

```module avail```

To load modules

```module load name```

where ```name``` is the module name, e.g.

```module load intel/19.0```

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

