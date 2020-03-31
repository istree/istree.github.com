---
layout: dev
title: log(Docker)
---
## 동작

컨테이너의 로그를 확인한다.

## 옵션

-f : 실시간으로 확인한다.

-tail 00 : 마지막 00 줄을 확인한다.

## 사용 예

이름이 my_wp인 컨테이너의 로그를 확인한다.

```
docker logs -f --tail 10 my_wp
```