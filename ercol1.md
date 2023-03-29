---
title: ercol1
date: 2023-03-28
---

ercol1
---

properties:

- CPUs: 4x [Intel Xeon Gold 6138 CPU @ 2.00GHz](https://ark.intel.com/content/www/us/en/ark/products/120476/intel-xeon-gold-6138-processor-27-5m-cache-2-00-ghz.html)
  <img style="float: right;" alt="Intel Xeon Gold 6138" width="150" src="/github-page-test/docs/assets/images/intel-xeon-gold.jpg">
  - 4x 20 cores, 160 virtual cores with HT
  - Cache: 27.5 MB L3
- RAM: 1 TB
- GPU: Nvidia Tesla V100S
  <img style="float: right;" alt="Nvidia Tesla V100S" width="200" src="/github-page-test/docs/assets/images/nvidia-tesla-v100s.jpg">

Accessible via:
- From within USM: ```ssh [user]@ercol1.usm.uni-muenchen.de```
- From outside:
  - [Via VPN](https://doku.lrz.de/display/PUBLIC/VPN+-+eduVPN) 
  - Via ```ltsp01``` (aka moon): ```ssh [user]@ltsp01.usm.uni-muenchen.de```; then inside ```ssh ercol1```
- you need to be part of the user group ```video``` to access the graphic card ([ask Tadziu](mailto:hoffmann@usm.uni-muenchen.de))

Storage:
- 80 TB on ```/data/auriga``` (shared with ercol1; not backed up)
- 12 TB on ```/e/ocean1```
- 2 TB on ```/e/scratch```

Support:
- channel #computing on Slack
