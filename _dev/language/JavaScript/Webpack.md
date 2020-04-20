---
title: Webpack
---

## 설치

npm이 설치되어 있어야 한다.

```bash
npm i webpack webpack-cli --save-dev
```

## 사용

index.js와 test.js를 bundle.js 파일로 합친다.

```bash
webpack src/index.js src/test.js -o dist/bundle.js
```

## 참고자료

[Guides - Getting Started](https://webpack.js.org/guides/getting-started/)

[Webpack 4 Tutorial](https://www.valentinog.com/blog/webpack/)