---
title: grep
---
파일 내의 텍스트를 검색해서 출력한다.

```bash
grep 검색어 파일명
```

예) 검색어 virtual을 현재 디렉토리의 모든 파일에서 찾는다.

```bash
grep virtual *
```

## 옵션

### -r
하위디렉토리 검색

예) 검색어 virtual을 하위 디렉토리까지의 모든 파일에서 찾는다.
```bash
grep -r virtual *
```

### -n
검색어가 위치한 줄 번호 표시

예) 검색어 virtual을 하위 디렉토리까지의 모든 파일에서 찾고 줄번호를 표시한다.
```bash
grep -rn virtual *
```