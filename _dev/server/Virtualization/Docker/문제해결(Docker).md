---
title: 문제해결(Docker)
---
## unauthorized: incorrect username or password.

docker login 명령어로 email 주소에 해당하는 id와 password를 입력해준다. id는 hub.docker.com에 가서 확인 가능하다.

## 윈도우에서 volume 마운트가 끊기는 문제

SMB v1을 해제하고 재부팅 하면 된다고 한다.

<https://github.com/docker/for-win/issues/2677>

## Docker컨테이너의 내부 네트워크에 직접 접근하기

```bash
route -p add 172.17.0.0 MASK 255.255.255.0 10.0.75.2
```

<http://www.programmersought.com/article/4030160285/>
