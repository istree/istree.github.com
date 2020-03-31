---
layout: dev
title: 시간 설정(Linux)
---
서버나 컨테이너의 시간이 기본적으로 Etc/UTC로 되어있다.

Asia/Seoul 로 변경할 경우 다음과 같다. 

```bash
ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
```