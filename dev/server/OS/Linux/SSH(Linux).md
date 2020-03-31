---
layout: dev
title: SSH(Linux)
---
## 설치

```bash
apt-get install openssh-server
```

## root 계정 접속 허용

설정 편집
```bash
vi /etc/ssh/sshd_config
```

다음 속성을 yes로 변경
```bash
PermitRootLogin yes
```

서버 재시작
```bash
service ssh restart
```

## 접속

```bash
ssh root@192.168.2.118
```