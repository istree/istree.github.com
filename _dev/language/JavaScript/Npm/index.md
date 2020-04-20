---
title: npm
---
## 설치

<https://github.com/nodesource/distributions>

nodejs 바이너리 배포판과 설정 및 지원 스크립트 를 사용하기위한 설명서

### v13.x

```bash
# 우분투 sudo 사용
curl -sL https://deb.nodesource.com/setup_13.x | sudo -E bash -
sudo apt-get install -y nodejs

# 데비안 root 설치 
curl -sL https://deb.nodesource.com/setup_13.x | bash -
apt-get install -y nodejs
```

## git 저장소에 있는 모듈 설치

```bash
npm install git+https://github.com/your/repo.git
```
