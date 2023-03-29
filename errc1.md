---
title: errc1
date: 2023-03-28
---

errc1
---

Properties:
- 4x [Intel Xeon CPU E7-4850 v2 @ 2.30GHz](https://ark.intel.com/content/www/us/en/ark/products/75248/intel-xeon-processor-e74850-v2-24m-cache-2-30-ghz.html)
  <img style="float: right;" alt="Intel Xeon E7-4850" width="300" src="/github-page-test/docs/assets/images/intel-xeon-e7.jpg">
  - 4x 12 physical cores; 96 virtual cores with HT
  - Cache: 24 MB L3
- RAM: 676 GB

Accessible via:
- From within USM: ```ssh [user]@errc1.usm.uni-muenchen.de```
- From outside:
  - [Via VPN](https://doku.lrz.de/display/PUBLIC/VPN+-+eduVPN) 
  - Via ```ltsp01``` (aka moon): ```ssh [user]@ltsp01.usm.uni-muenchen.de```; then inside ```ssh errc1```
- [jupyter-notebook](https://errc1.usm.uni-muenchen.de:9999)

Storage:
- 80 TB on ```/data/auriga``` (shared with ercol1; not backed up)
- 30 TB on ```/e/arch/``` (backed-up weekly, see [backup](backup.md))
- 1.1 TB on ```/scratch/```

Support:
- channel #computing on Slack
