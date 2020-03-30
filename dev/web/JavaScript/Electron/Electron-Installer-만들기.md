---
layout: dev
title: Electron Installer 만들기
---
## electron-builder 설치

```bash
npm install --save-dev electron-builder@20.39.0
```

## package.json

플랫폼별 빌드 명령어 추가

플랫폼별 빌드 옵션 추가

```json
{
  "name": "your-app",
  "version": "0.1.0",
  "main": "index.js",
  "scripts": {
    "start": "electron .",
    "build:osx": "build --mac",
    "build:linux": "npm run build:linux32 && npm run build:linux64",
    "build:linux32": "build --linux --ia32",
    "build:linux64": "build --linux --x64",
    "build:win": "npm run build:win32 && npm run build:win64",
    "build:win32": "build --win --ia32",
    "build:win64": "build --win --x64"
  },
  "devDependencies": {
    "electron-builder": "^20.39.0"
  },
  "build": {
    "productName": "HelloElectron",
    "appId": "com.electron.hello",
    "asar": true,
    "protocols" : {
        "name" : "helloElectron",
        "schemes" : ["helloelectron"]
    },
    "mac": {
      "target": [
        "default"
      ],
      "icon": "./resources/installer/Icon.icns"
    },
    "dmg": {
      "title": "HelloElectron",
      "icon": "./resources/installer/Icon.icns"
    },
    "win": {
      "target": [
        "zip",
        "nsis"
      ],
      "icon": "./resources/installer/Icon.ico"
    },
    "linux": {
      "target": [
        "AppImage",
        "deb",
        "rpm",
        "zip",
        "tar.gz"
      ],
      "icon": "./resources/linuxicon"
    },
    "nsis":{
      "oneClick" : false,
      "allowToChangeInstallationDirectory" :true
    },
    "directories": {
      "buildResources": "resources/installer/",
      "output": "dist/",
      "app": "."
    }
  }
}
```

## 빌드 실행

Mac
```bash
npm run build:osx
```

Windows
```bash
npm run build:win
```

Linux
```bash
npm run build:linux
```

## 멀티플랫폼 빌드 설정

하나의 OS에서 다른 OS의 빌드를 실행할 수도 있다.

Mac 에서 Window 빌드
```bash
brew install wine --without-x11
brew install mono
```

Mac 에서 Linux 빌드
```bash
brew install gnu-tar graphicsmagick xz
brew install rpm
```

## 멀티플랫폼 빌드 실행

package.json 파일의 scripts에 다음과 같이 추가
```bash
"build": "npm run build:linux && npm run build:osx && npm run build:win"
```

다음 명령어 실행
```bash
npm run build
```