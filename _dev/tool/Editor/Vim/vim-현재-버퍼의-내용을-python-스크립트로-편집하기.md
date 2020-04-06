---
title: vim 현재 버퍼의 내용을 python 스크립트로 편집하기
---
기본적인 정규식 치환으로 힘든 편집을 해야할때, 예를들어 수천라인의 json 파일의 특정 필드값에 날짜 값을 순서대로 넣는다던지, 특정 난수를 발생시켜서 집어 넣는다던지 할때 python을 활용할 수 있다.

[if_pyth](http://vimdoc.sourceforge.net/htmldoc/if_pyth.html)를 사용한다.

vim에서 version 확인시  2.x의 경우 +python/dyn, 3.x의 경우 +python3/dyn 이 보여야 한다.

스크립트는 다음과 같이 입력한다.

예) 전체 영역에 스크립트 적용

```vim
:%py << endPython
# 스크립트 내용 ...
endPython
```

예) visual block 지정 시
```vim
:'<,'>py << endPython
# 스크립트 내용 ...
endPython
```

예) json 파일에서 'value' 가 포함된 줄의 값을 0~100까지 random으로 발생시켜서 치환한다.

```python
import sys, vim
import datetime, time, random
import re
p = re.compile("value")
for i, line in enumerate(vim.current.buffer):
    if p.search(line):
        vim.current.buffer[i] = "\t\t\"value\": %s" % random.randint(0,100)
```

예) json 파일에서 'time' 이 포함된 줄을 특정 시간으로 부터 1분씩 증가하며 치환한다.

```python
import sys, vim
import datetime, time 
import re
timeValue = datetime.datetime(2015,12,12,9,0,0)
p = re.compile('time')
for i, line in enumerate(vim.current.buffer) :
    if p.search(line):
        timeValue += datetime.timedelta(minutes=1)
        vim.current.buffer[i] = "\t\t\"time\": \"%s\"," % timeValue
```