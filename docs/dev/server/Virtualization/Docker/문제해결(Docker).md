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

## 윈도우에서 컨테이너가 시작되지 않을 때

가끔 윈도우 재부팅 후 포트가 죽지않고 남아있어 컨테이너가 시작되지 않는 경우가 있다.

콘솔을 열어 다음 명령어로 포트 번호를 사용하는 PID를 확인한다.

```bash
netstat -nao
```

해당하는 PID에 대해 다음 명령어를 실행해서 포트를 죽인다.

```bash
taskkill /f /pid PID
```

이후 윈도우를 재부팅 하면 자동으로 올라온다. 

그렇지 않은 경우 docker start 등으로 수동으로 재시작 해준다.
