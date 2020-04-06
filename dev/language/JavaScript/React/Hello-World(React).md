---
title: Hello-World(React)
---
대부분 예제들이 node로 되어있지만

단순히 실행만 해보기 위해서 이므로 다음과 같이 작성한다.

## main.js

```javascript
const element = (
  <div>
  <h1>Hello, world!</h1>
  </div>
);
ReactDOM.render(
  element,
  document.getElementById('hello')
);
```

## index.html

```html
<html>
<head>
  <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
  <script src="https://unpkg.com/react@16/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
  <script type="text/babel" src="main.js"></script>
</head>
<body>
  <div id="hello"></div>
</body>
</html>
```

## 실행

소스가 있는 디렉토리에서 (python이나 SimpleHTTPServer가 없으면 설치한다.)

```bash
python -m SimpleHTTPServer
```

웹브라우저로 확인한다. <http://localhost:8000>