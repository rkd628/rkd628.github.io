---
layout: post
title:  "트러블슈팅"
date:   2022-04-03 21:03:39 +0530
categories: RaspberryPi
---

# 메모리 부족

```
$sudo pip install firebase-admin
```

진행이 안됨..   
워낙 라즈베리파이 메모리가 적어서 그런걸로 의심.  
내키진 않지만 swap 메모리 늘리기로 결정.

```
$sudo vi /etc/dphys-swapfile
# CONF_SWAPSIZE 변경
$sudo /etc/init.d/dphys-swapfile restart
```

```
$ free -h
              total        used        free      shared  buff/cache   available
Mem:          871Mi       100Mi       547Mi       7.0Mi       224Mi       710Mi
Swap:         1.0Gi          0B       1.0Gi
```

이제서야 진행 됨.

