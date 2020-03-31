---
layout: dev
title: exec(Docker)
---
## 동작

컨테이너에 명령어를 실행한다.

## 옵션

-it : 터미널 입력을 허용한다.

## 사용 예

이름이 mysql_57인 컨테이너에 bash를 실행하여 접속한다.

```
docker exec -it mysql_57 /bin/bash
```

이름이 mysql_57인 컨테이너에 mysql 클라이언트 프로그램을 실행하여 root 계정으로 접속한다.

```
docker exec -it mysql_57 mysql -u root -p
```