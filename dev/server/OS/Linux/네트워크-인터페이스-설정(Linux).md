---
layout: dev
title: 네트워크 인터페이스 설정(Linux)
---
설정파일 열기

```bash
vi /etc/network/interfaces
```

다음과 같이 편집 후 저장
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.2.20
netmask 255.255.255.0
gateway 192.168.2.1
network 192.168.0.0
broadcast 192.168.10.255
dns-nameservers 8.8.8.8
```
address, netmask, gateway 세개만 있어도 동작한다.

서비스 재시작
```bash
service networking restart
```