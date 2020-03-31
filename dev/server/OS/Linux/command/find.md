---
layout: dev
title: find
---
현재 디렉토리 및 하위 디렉토리에서 .DS_Store 파일을 검색한다.

```
find ./ -name ".DS_Store" -print
```

현재 디렉토리 및 하위 디렉토리에서 .DS_Store 파일을 삭제한다.
```
find ./ -name ".DS_Store" -exec rm {} \;
```

현재 디렉토리 및 하위 디렉토리의 모든 디렉토리의 권한을 755로 변경한다.
```
find ./ -type d -exec chmod 755 {} \;
```

현재 디렉토리 및 하위 디렉토리의 모든 파일의 권한을 644로 변경한다.
```
find ./ -type f -exec chmod 644 {} \;
```

find exec 사용시 끝에 \;를 붙여주지 않으면 find: -exec: no terminating ";" or "+" 오류가 발생한다.