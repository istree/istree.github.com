---
title: Ruby
---

## Rbenv를 사용하여 Ruby 설치하기

### ruby-build tool  설치

```bash
sudo apt update
sudo apt install git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev
```

### rbenv와 ruby-build 스크립트 설치

```bash
curl -sL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer | bash -
```

### rbenv 경로 추가

```bash
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
```

### Ruby 설치

```bash
rbenv install 2.5.1
rbenv global 2.5.1
```

### 설치된 Ruby 버전 확인

```bash
ruby -v
```

## 참고자료

[Debian9에서 Ruby 설치](https://linuxize.com/post/how-to-install-ruby-on-debian-9/)
