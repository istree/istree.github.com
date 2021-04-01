---
title: 사용자 정보
---

git config로 사용자 이름과 이메일 주소를 설정한다.  
commit이나 push할 경우 변경하기 상당히 까다롭기 때문에 최대한 정확해야 한다.

git config는 세가지 옵션이 있다.

* --system : /etc/gitconfig 파일, 시스템 전역 설정 
* --global : ~/.gitconfig 파일, 사용자별 설정
* --local : .git/config 파일, 저장소 별 설정

옵션을 입력하지 않을 경우 기본 옵션은 --local 이다.

이름
```bash
git config --global user.name "your name"
```

이메일
```bash
git config --global user.email "yourname@example.com"
```

이름 확인
```bash
git config user.name
```

모든 정보 확인
```bash
git config --list
```
