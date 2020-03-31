---
layout: dev
title: 저장소 이전(Git)
---

서버에 빈 저장소를 생성한다.

--mirror 옵션을 적용하여 이전 저장소를 내려받는다. 
```bash
git clone --mirror http://site/old.git
```

디렉토리 이동
```bash
cd old.git
```

새로운 저장소 지정
```bash
git remote set-url --push origin http://site/new.git
```

원격 저장소로 push 한다.
```bash
git push --mirror
```
