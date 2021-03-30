---
title: 윈도우 Docker 설치
---
## 종류

Docker Tool Box : VirtualBox 기반

Docker Desktop for Windows : Hyper-V 기반

구 버전 윈도우에 사용해야되는게 아니라면 가능한 Hyper-V 기반의 Docker Desktop for Windows가 낫다.

[Docker Desktop for Windows 다운로드](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

## OS 선택

윈도우10 Pro 이상에 Hyper-V가 탑재되어 있다.

## 컨테이너 선택

리눅스 컨테이너와 윈도우 컨테이너를 선택할 수 있다.

윈도우 컨테이너는 Hyper-V 로 사용해도 되므로 리눅스 컨테이너를 선택한다.

## 자동 로그인

윈도우 시작시 로그인 하지 않으면 Docker Service가 올라오지 않으므로 자동 로그인 설정이 필요하다.

1. <실행> 에서 NETPLWIZ를 입력하면 사용자 계정 탭이 나타난다.

2. 사용자 이름과 암호를 입력해야 이 컴퓨터를 사용할 수 있음. 항목을 <해제>한다.

3. <적용> 선택 후 기본으로 로그인 할 사용자와 암호를 입력한다.
