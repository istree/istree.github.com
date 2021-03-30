---
title: GitLab
---
## 설치

open ssh 설치
```
apt-get update
apt-get install curl
apt-get install openssh-server
apt-get install ca-certificates
```

postfix 설치
```
apt-get install -y postfix
```

gitlab sh 실행
```
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
```

설치
```
apt-get install gitlab-ce
```

재설정
```
gitlab-ctl reconfigure
```

시작
```
gitlab-ctl start
```

## 업데이트

apt 업데이트
```
apt-get update
```

apt 설치시 버전을 확실히 지정해 줘야 한다.
```
apt-get install gitlab-ce=8.17.7-ce.0
```

버전에 따라 업데이트를 단계적으로 해주어야 한다.

예를들어 8.x 대라면 8.x 의 가장 마지막 버전으로 업데이트 한 후 9.x로 넘어가야한다.

관련 글 [GitLab Maintenance Policy](https://docs.gitlab.com/ee/policy/maintenance.html)

## 백업

```bash
gitlab-rake gitlab:backup:create
```
/var/opt/gitlab/backups 위치에 1550730800_2019_02_21_gitlab_backup.tar 식으로 백업 파일이 생긴다.

## 복구

/var/opt/gitlab/backup 위치에 백업한 파일을 넣고 아래 명령어에서 BACKUP 변수에 날짜까지만 넣어준다.

```
gitlab-rake gitlab:backup:restore BACKUP=1550730800_2019_02_21
```

## 도커

[도커 gitlab-ce](https://hub.docker.com/r/gitlab/gitlab-ce/)

[도커 gitlab-ce 태그](https://hub.docker.com/r/gitlab/gitlab-ce/tags/)

[GitLab Docker images](https://docs.gitlab.com/omnibus/docker/)

## 참고자료

[설치형 GiLab CE 설치형 8.5에서 10.4로 업데이트](http://blog.devenjoy.com/?p=493)

[GitLab Configuration](https://docs.gitlab.com/omnibus/settings/configuration.html)

[Gitlab Backup & Restore 방법](https://cdecl.net/312)

## 문제 해결

#### ruby_block[supervise_redis_sleep] action run 오류

runsv가 없을 경우에 실행해줘야 한다.

```
/opt/gitlab/embedded/bin/runsvdir-start
```

관련 포스팅 https://gitlab.com/gitlab-org/omnibus-gitlab/issues/160

#### 실수로 로그인을 비활성화 한 경우 로그인 활성화

https://gitlab.com/gitlab-org/gitlab-ce/issues/37795

#### Forbidden 메시지만 출력될 경우

Gitlab이 해킹을 감지해서 IP를 블록했기 때문에 해제해주어야 한다.

http://airpage.org/xe/project_data/26897
