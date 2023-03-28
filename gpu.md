---
title: gpu
date: 2023-03-28
---

gpu
---

CUDA can be set via including the following lines in ```~/.profile```

```
 export PATH="/usr/local/cuda-10.1/bin:$PATH" 
 export LD_LIBRARY_PATH="/usr/local/cuda-10.1/lib64:$LD_LIBRARY_PATH"
```

To check if the gpu is working properly type

```nvidia-smi```

Or

```watch -n 1 nvidia-smi```

The same but updated every second. Command ```nvidia-smi``` is the equivalent of ```top``` for the CPU.

NOTE: to use the GPU card you need to ask Tadziu to be added to the video user group.

