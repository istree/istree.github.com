---
title: DNS 설정(Linux)
---
설정파일 열기
```bash
vi /etc/resolvconf/resolv.conf.d/head
```

다음과 같이 편집
```bash
nameserver 8.8.8.8
```

서비스 재시작
```
service resolvconf restart
```