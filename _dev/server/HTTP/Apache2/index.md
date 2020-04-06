---
title: Apache2
---

## 설치

```bash
apt-get install apache2
```

## 설정 항목 (2.4)

/etc/apache2 : 설정 디렉토리

apache2.conf : 공통 설정파일

mods-available : 사용 가능한 모듈

mods-enabled : 활성된 모듈

conf-available : 사용 가능한 설정

conf-enabled : 활성된 설정

sites-enabled : 가상호스트 설정

## 모듈 (2.4)

아파치 루트 디렉토리 내에 mods-available 디렉토리와 mods-enabled 디렉토리가 있다.

각 모듈들은 mods-available 디렉토리 내에 파일별로  미리 정의되어있고 원하는 모듈에 해당하는 파일을 mods-enabled 디렉토리에 복사하거나 심볼릭 링크를 생성해주면 된다.

```bash
cd /etc/apache2/mods-enabled
ln -s ../mods-available/proxy.load proxy.load
ln -s ../mods-available/proxy_http.load proxy_http.load
```

## 프록시 (2.4)

프록시 사용을 위해서 proxy_module, proxy_http_module 이 필요하다.

```bash
LoadModule proxy_module /usr/lib/apache2/modules/mod_proxy.so
LoadModule proxy_http_module /usr/lib/apache2/modules/mod_proxy_http.so
```

VirtualHost 설정에 다음 내용을 추가한다.
```bash
ProxyRequests Off
ProxyPreserveHost On
ProxyPass /gitlab http://192.168.2.22/gitlab
ProxyPassReverse /gitlab http://192.168.2.22/gitlab
```

* ProxyRequests : 포워드 프록시 사용시 On, 리버스 프록시 사용시 Off
* ProxyPreserveHost : 포워드 프록시 사용시 Off, 리버스 프록시 사용시 On
* ProxyPass : 프록시에 연결할 URL을 기술한다.
* ProxyPassReverse : WAS의 HTTP 응답 헤더를 수정하여 클라이언트에 전달한다. 이 과정이 없으면 클라이언트가 redirect시 제대로 연결할 수 없으므로 꼭 설정한다.

서비스 재시작
```bash
apachectl restart
```

## 기타

### 디렉토리 리스팅 비활성화

index가 없을경우 디렉토리 목록이 나타날 경우 비활성화 하는 것이 좋다.

/etc/apache2/apache2.conf 를 연다.

다음과 같이 되어있다면
```apache
<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>
```

다음과 같이 Options에서 Indexes를 삭제한다.
```apache
<Directory /var/www/>
        Options FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>
```

### 로그 안쌓이게 하기
로그가 쌓여서 불필요하게 디스크 공간이 낭비되거나 로그가 필요없는 시스템은 로그를 쌓지 않는게 좋다.

로그는 AccessLog ErrorLog CustomLog의 3가지가 있다. 

AccessLog와 CustomLog는 주석 처리를 해주면 쌓이지 않지만 ErrorLog는 주석 처리를 해도 계속 쌓인다.

ErrorLog를 /dev/null 로 보내면 쌓이지 않는다.

```apache
ErrorLog /dev/null
```

### AH00558: apache2: could not reliably determine the server's fully qualified domain name

서버 시작시 경고가 해당 경고가 발생하는 경우가 있다. 이는 서버의 도메인 이름을 확인할 수 없다는 뜻이다.

apache2.conf에 ServerName 항목을 추가한다.

```apache
ServerName localhost
```

## Docker

docker 컨테이너의 command는 foreground로 실행해야 제대로 동작한다.

apachectl과 같은 프로그램은 apache를 background로 실행하기 때문에 제대로 동작하지 않으므로 FOREGROUND 옵션을 적용한다.

```bash
apachectl -D FOREGROUND
```

## 참고자료

[Configure Apache as a reverse proxy](http://www.microhowto.info/howto/configure_apache_as_a_reverse_proxy.html)