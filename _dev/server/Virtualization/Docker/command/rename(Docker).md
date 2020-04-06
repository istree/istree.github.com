---
title: rename(Docker)
---
## 동작
컨테이너의 이름을 바꾼다.

export 된 컨테이너 여러개를 import할때 충돌 방지를 위해 이름을 바꿔주는 것이 좋다.

## 사용예
gitlab_811 컨테이너의 이름을 gitlab_811_origin 으로 바꾼다.
```
docker rename gitlab_811 gitlab_811_origin
```