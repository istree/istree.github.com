---
layout: dev
title: rbenv가 설치된 jenkins 이미지 만들기
---
dockerfile 예제

```docker
FROM jenkins/jenkins:lts
USER root
RUN apt update
RUN apt install -y git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev
ENV PATH="/root/.rbenv/bin:/root/.rbenv/shims:${PATH}"
RUN curl -sL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer | bash -; exit 0
RUN echo 'export PATH="/root/.rbenv/bin:/root/.rbenv/shims:$PATH"' >> ~/.bashrc
WORKDIR $JENKINS_HOME
```