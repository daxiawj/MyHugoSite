---
title: "Linux 'date' Command usage"
tags:
  - Linux
  - Server
  - Bash
  - 技术
date: 2014-02-24 14:50:57
category: 技术
---

 *nix `date` is quite powerful tool for date manipulation.

```bash
for idate in `seq 0 1461`
do
  thedate=`date +%Y%m%d -d "20100101 + $idate"`
  echo $thedate
done
```
etc.