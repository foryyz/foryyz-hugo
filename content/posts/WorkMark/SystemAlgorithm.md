---
title: '操作系统与算法'
date: 2024-06-06T09:40:53+08:00
draft: false
---
# 时间片轮转算法 - RR

## 思想&规则

- 思想：公平地，轮流地为各个进程服务，让每一个进程在一定时间间隔内都可以得到响应。
- 规则：按照各个进程到达就绪队列的顺序，轮流让各个进程执行一个**时间片**（比如100ms）。若进程未在一个时间片内执行完，则剥夺处理机，将进程重新放到就绪队列队尾重新排队
- 抢占式 - 时间片用完，便被强行掠夺
- 不会导致饥饿

## 优点

- 公平，适用于分时系统

## 缺点

- 频繁切换有开销，不区分优先级

## 时间片大小的设定

- 如果时间片太大了，这个算法就会退化成先到先服务调度算法，响应时间会被增大，因此时间片不能太大！
- 如果时间片太小，则进程切换就会过于频繁，会浪费很多性能和时间！所以时间片也不宜太小



# 读写者问题

## 进程类型

- Reader - 只读不写
- Writer - 只写不读

## 条件：

1. 任意多个读进程可以同时读这个文件
2. 一次只有一个写进程可以往文件里写
3. 如果一个写进程正在进行操作，禁止任何读进程文件

## 算法类型

- 读者优先
- 写者优先
- 读写公平