---
title: "pyspark 실행 시 executor와 driver 간의 python minor 버전이 일치하지 않을 때"
date: 2019-08-22T22:23:46+09:00
draft: false
noSummary: true

categories: ['Code', 'Solution']
tags: ['spark', 'pyspark', 'version_conflict']
author: "cookieshake"
---

##### 문제점

pyspark 실행 시 driver와 executor의 python 버전이 일치하지 않는다는 메시지가 뜨거나, 특정 패키지를 import하는데 실패하거나, 알 수 없는 에러 메세지가 뜬다.

##### 원인

driver와 executor간의 python minor 버전이 일치하지 않는다.

##### 해결방법

1. `spark.pyspark.python` config를 이용한다.

하지만 이유를 알 수 없이 계속 executor에서 2.6버전의 python이 실행되었다.

2. pyspark를 호출하는 장비의 `PYSPARK_PYTHON` 환경변수를 이용한다.
