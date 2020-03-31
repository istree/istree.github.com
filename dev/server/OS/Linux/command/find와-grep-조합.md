---
layout: dev
title: find와 grep 조합
---
grep -r 옵션이 동작하지 않을경우나 파일명에 정규식을 적용해서 필터링 할 경우에 find와 grep를 조합해서 사용한다.

예) 확장자가 conf인 파일을 하위 디렉토리까지 찾고 검색어 virtual이 포함된 위치를 출력한다.
```bash
find ./ -name '*.conf' | xargs grep -n 'virtual'
```

xargs를 사용하는 이유는  find된 각각의 파일명에 대해 grep를 실행하기 위함이다.

xargs를 사용하지 않는 경우 find의 결과에 대해서 grep를 실행한다.

예) 확장자가 conf인 파일을 하위 디렉토리까지 찾고 파일명에 검색어 default가 포함된 목록을 출력한다.
```bash
find ./ -name '*.conf' | grep 'default'
```