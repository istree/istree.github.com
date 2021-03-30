---
title: Portainer
---
## 설치

다음 명령어로 설치할 수 있다.

```bash
$ docker volume create portainer_data
$ docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

## 문제해결

### vi 편집기 동작 오류

콘솔에서 vi편집기가 동작하지 않는 오류가 있다. vim 대신 vim-tiny를 사용하면 해결할 수 있다.

vi 입력 모드에서 한글 입력 시 WebSocket is already in CLOSING or CLOSED state. 오류가 발생하며 콘솔이 먹통이 되므로 주의한다.

```bash
apt-get install vim-tiny
```

### vi 한글입력 오류

한글 입력이 필요하거나 굳이 한글을 안쓰더라도 실수로 한글을 입력하여 먹통이 되는 것이 불편한 경우 한글 입력을 설정해준다.

locale 설치 

```bash
apt-get install -y locales locales-all
```

.bash_profile에 환경변수 추가

```bash
export LANGUAGE=en_US.UTF-8
export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8
```

```bash
source .bash_profile
```

컨테이너 생성시 Console 옵션을 반드시 Interactive & TTY (-i -t) 로 해야 제대로 동작한다.

.bash_profile의 내용을 컨테이너 생성시 ENV에 입력해주어도 된다.

## 참고자료

[portainer 홈](https://www.portainer.io/)

[portainer 설치](https://www.portainer.io/installation/)
