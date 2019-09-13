---
title: "unprivileged container에 snapd가 설치되지 않을 때"
date: 2019-09-13T23:06:33+09:00
draft: false
noSummary: true

categories: ['Code', 'Solution']
tags: ['lxc', 'lxd', 'unprivileged', 'container']
author: "cookieshake"
---

##### 문제점

unprivileged container에 snapd 설치 시 squashfs 관련 에러가 발생하며 설치가 실패한다

##### 원인

...잘 모르겠지만 squashfs를 unprivileged container에서 이용할 수 없다

##### 해결방법

1. `squashfuse` 설치 이후 `snapd`를 설치한다.

ubuntu의 경우

``` bash
apt-get install -y squashfuse
apt-get install -y snapd
```
