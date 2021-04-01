---
title: 커밋 메시지 수정
---

### 가장 최근의 커밋 메시지 수정
```bash
git commit --amend
```

### 특정 커밋의 메시지 수정
수정하고 싶은 커밋의 바로 전 hash 값을 확인한다.
hash 값이 342f5f3일 경우

명령어를 입력
```bash
git rebase -i -p 342f5f3
```

다음과 같이 커밋 내역이 편집기로 실행된다.
```vim
pick 342f5f3 커밋 메시지
.
.
```

여기서 편집을 원하는 부분의 pick을 edit로 고치고 저장후 종료한다.  
edit 외에도 drop(삭제) reword(메시지수정) 등도 가능하다.

작성자를 수정한다.
```bash
git commit --amend --author="name<email@example.com>"
```

rebase 대상이 여러개일 경우 다음으로 진행한다.
```bash
git rebase --continue
```

서버에 push 한다. 이력을 고쳤기 때문에 강제로 push 해야 한다.
```bash
git push origin +master
```