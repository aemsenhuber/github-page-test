---
title: profilers
date: 2023-03-28
---

profilers
---

To profile with MPI use

```mpirun -n 10 amplxe-cl -collect hotspots -r ./result_folder -- ./executable```

where you are using 10 ranks, with Amplifier, you collect hotspots, the results are in the result_folder (one subfolder per rank), and your executable is the last argument.

Note that executable has to be compiled with profile options (e.g. -pg).

To load the results use the Amplifier GUI

```amplxe-gui &```

start a project with the given executable and load the rank subfolders via Import Results button. 

Each rank has to be analyzed individually.

Analogously to profile vectorization with MPI use

``` mpirun -n 10 advixe-cl -collect survey -- ./executable```

and

```advixe-gui &```

To analyze threads with MPI

```mpirun -np 10 inspxe-cl -collect mi2 -r profile ./mocassin```

and

```inspxe-gui &```

