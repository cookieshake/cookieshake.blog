---
title: "traefik helm 설치 시 hostPort가 동작하지 않을 때"
date: 2019-08-18T21:03:31+09:00
draft: false
noSummary: true

categories: ['Code', 'Solution']
tags: ['kubernetes', 'k8s', 'traefik', 'helm', 'CNI']
author: "cookieshake"
---

##### 문제점

traefik을 helm을 통해 설치하며 config로 `deployment.hostPort.httpEnabled` 및 `deployment.hostPort.httpsEnabled`를 지정하였는데도 pod이 실행되는 host의 80, 443 포트가 열리지 않는다.

##### 원인

CNI 중에 deployment의 hostPort 기능을 제대로 지원하지 않는 CNI가 있다.

##### 해결방법

1. traefik deployment의 `hostNetwork`를 `true`로 변경한다. 

``` yaml
spec:
	hostNetwork: true
```

2. CNI에 hostPort 기능을 추가한다. 사용중인 CNI에 따라 다르다.