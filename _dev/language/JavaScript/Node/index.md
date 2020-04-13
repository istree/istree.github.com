---
title: Node.js
---

## 파일을 읽어서 실행

webpack과 node에서 동일한 모듈을 사용하고 싶은 경우가 있다.

공통의 prop.js 파일이 있는 경우 브라우저에서는 다음과 같이 사용한다면

```javascript
<script type="text/javascript" src="./../common/prop.js"></script>
```

Node에서는 다음과 같이 사용할 수 있다.

```javascript
var fs = require('fs');
eval( fs.readFileSync('example/common/prop.js') + '', 'utf8');
```

[관련질의](https://stackoverflow.com/questions/5797852/in-node-js-how-do-i-include-functions-from-my-other-files)

## 참고자료

[v12.16.2 API (LTS)](https://nodejs.org/dist/latest-v12.x/docs/api/)
