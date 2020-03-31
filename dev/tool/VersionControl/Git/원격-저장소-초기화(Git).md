---
layout: dev
title: 원격 저장소 초기화(Git)
---
로컬 저장소의 .git 디렉토리를 삭제한다.

로컬 저장소에서 git init을 다시 수행하여 초기화 시킨다.

초기화에 등록될 파일을 추가 및 커밋한다.

```bash
git add .
git commit -m 'Initial commit'
```

초기화 시킬 원격 저장소를 추가시킨다.
```bash
git remote add origin <url>
```

현재 상태를 원격저장소에 적용시킨다.
```bash
 git push --force --set-upstream origin master
```

또는 master branch를 삭제한다.
```bash
git push origin --delete master
```
