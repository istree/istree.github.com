---
layout: dev
title: Electron App 만들기
---
## 개요

Electron 앱은 Node.js 앱이라고 할 수 있다.

Node.js 모듈과 마찬가지로 시작점은 package.json 이다.

대부분의 Electron 앱은 다음과 같은 구조를 갖는다.

```
your-app/
├── package.json
├── index.js
└── index.html
```

## 초기화

빈 폴더를 생성한 후 폴더 안으로 이동해서 다음 명령어를 실행한다.

```bash
npm init
```

npm은 기본적인 package.json 파일을 생성한다.


## package.json

입력 프롬프트를 기본값으로 넘길 경우 생성되는 package.json 파일은 다음과 같다.

```json
{
  "name": "your-app",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}
```

## Electron 설치

```bash
npm install --save-dev electron
```

## index.js

다음은 창을 여는 애플리케이션이다.

```javascript
const { app, BrowserWindow } = require('electron')

function createWindow () {
  let win = new BrowserWindow({ width: 800, height: 600 })
  win.loadFile('index.html')
}

app.on('ready', createWindow)
```

## index.html

보여주고 싶은 웹 페이지를 다음과 같이 만든다.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Hello World!</title>
  </head>
  <body>
    <h1>Hello World!</h1>
  </body>
</html>
```

## 실행

package.json 파일을 열고 scripts 항목 하위에 **"start": "electron ."** 을 추가한다.

```json
{
  "name": "your-app",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "electron ."
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "electron": "^6.0.2"
  }
}
```

다음 명령어를 실행하면 앱이 동작한다.

```bash
npm start
```

## 예제 수정

크롬 개발자 도구를 열고, Mac OS에서 Cmd+Q를 누르기 전에는 모든 창이 닫혀도 종료되지 않는 기능을 추가한다.

index.js를 다음과 같이 편집후 실행한다.

```javascript
const { app, BrowserWindow } = require('electron')
let win
function createWindow () {
  let win = new BrowserWindow({ width: 800, height: 600 })
  win.loadFile('index.html')
  win.webContents.openDevTools()
  win.on('closed', () => {
    win = null
  })
}

app.on('ready', createWindow)

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') {
    app.quit()
  }
})
```