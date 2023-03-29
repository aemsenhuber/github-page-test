---
title: c2pap
date: 2023-03-28
---

c2pap
---

properties:

- CPUs:

  - 2x [Intel Xeon CPU E5-2697 v3 @ 2.60GHz](https://ark.intel.com/content/www/us/en/ark/products/81059/intel-xeon-processor-e52697-v3-35m-cache-2-60-ghz.html)
  <img style="float: right;" alt="Intel Xeon Gold 6138" width="250" src="/github-page-test/docs/assets/images/intel-xeon.jpg">

  - 32 kB L1 per core, 256 kB L2 cache per core, 4x18 MB L3 cache (shared)

  - number of nodes: 120

  - cores per node: 28 (56 with HT)

  - memory per node: 64 GB

- GPUs:

  - 4x NVIDIA A100 40GB

  - One GPU is reserved for access via slurm jobs. The remaining 3 GPUs are available via the cloud computing interface as the flavours pr85tu.nvidia-a100.1 (1 GPU), pr85tu.nvidia-a100.2 (2 GPUs), or pr85tu.nvidia-a100.3 (3 GPUs)

- storage:

  - 2Tb in work directory ```/gpfs/work/pr83pa```

  - 100 GB in ```home``` directory

accessible via:

  - ssh:
    ```user@lxloginc2pap.lrz.de```

  - you need to be part of our project ```pr83pa``` (Dispersal of planetary discs by X-ray photoevaporation) to access it ([contact me](mailto:picogna@usm.lmu.de))

- more info at [c2pap wiki](https://wiki.tum.de/display/origins/C2PAP)
