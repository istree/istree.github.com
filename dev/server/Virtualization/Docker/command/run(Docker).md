---
layout: dev
title: run(Docker)
---
## 동작

컨테이너 이미지가 없으면 pull한 후 create하고 start한다.

컨테이너에 명령어를 전달하지 않는다면 생성하자마자 종료된다.

컨테이너는 프로세스이므로 실행중인 프로세스가 없으면 컨테이너는 종료되기 때문이다.

## 옵션

-d : detached mode 일명 백그라운드 모드

-p : 호스트와 컨테이너의 포트를 연결해준다.

-v : 호스트와 컨테이너의 디렉토리를 연결한다.

-e : 컨테이너 내에서 사용할 환경변수

--name : 컨테이너 이름, 생략할 경우 docker 자동으로 이름을 짓는다.

-rm : 프로세스 종료시 컨테이너를 자동으로 제거한다.

-it : 터미널에 입력할 수 있다. (input terminal)

-link : 컨테이너를 연결한다.

--restart : 컨테이너 재시작 옵션 상시 실행하고 싶은 경우 "always"를 사용한다.

## 사용 예

우분투 16.04를 실행한다.
```
docker run ubuntu:16.04 
```

우분투 최신 버전을 실행한다.
```
docker run ubuntu:latest
```

bash를 실행하고 입력이 가능하게 한다. 프로세스 종료시 컨테이너가 삭제된다.
```
docker run --rm -it ubuntu:16.04 /bin/bash
```

MySQL 5.7 버전을 mysql_57 이름으로 3306 포트에 연결하고 백그라운드로 실행한다.
```
docker run -d -p 3306:3306 -e MYSQL_PASSWORD=mypassword --name mysql_57 mysql:5.7
```

워드프레스를 my_wp 이름으로 8080포트에 연결하고  mysql_57에 연결하고  백그라운드로 실행한다.

```
docker run -d -p 8080:80 
  --link mysql_57:mysql 
  -e WORDPRESS_DB_HOST=mysql 
  -e WORDPRESS_DB_NAME=wp 
  -e WORDPRESS_DB_USER=wpuser
  -e WORDPRESS_DB_PASSWORD=wppwd
  - name my_wp 
  wordpress
```