---
layout: post
title: shared memory
subtitle: 
author: frank
date: 2018-04-16 23:25:00 +0800
categories: 
tag: 
---
## shared memory in linux is like /dev/tmp 
```
in df -h
tmpfs              38G  5.0G   33G  14% /run
tmpfs              95G   29G   66G  31% /dev/shm
tmpfs             5.0M     0  5.0M   0% /run/lock
tmpfs              95G     0   95G   0% /sys/fs/cgroup
tmpfs              95G  4.0G   91G   5% /tmp
```

shared memory will lost when the machine restart, however when the process restart ,you can still get the shared memory
through file descriptor.

however if you use memory in the process, when the process need to restart, the content of the memory will be lost.


### shared memory in message processing agent

when using shared memory as the message process agent, we can use shared memory as the temporary storage, if the machince not restart
the content will not be lost.
