---
title: Nginx
---
## 설정

/etc/nginx/nginx.conf 메인 설정 파일

대략적인 구조는 다음과 같이 http 아래 여러 server를 포함한다.

```nginx
http {
    server {
    }
    ...
}
```

기본 설정은 include 지시자로 conf.d 디렉토리 내의 하위 설정 파일을 모두 포함하도록 되어있다.

```nginx
http {
    include /etc/nginx/conf.d/*.conf
}
```

## 프록시

프록시 설정이 매우 간단하다.

/gitlab 경로를 다른 내부 서버로 포워드하는 경우

conf.d 내에 proxy.conf 파일을 만든다.

```nginx
server {
    listen 80;
    server_name localhost;
    
    location /gitlab {
        proxy_pass http://10.0.1.10:9021/gitlab;
    }
}
```

세미콜론 ;을 안해주면 오류가 발생하므로 주의한다.

## 문제해결 

### 413 Request Entity Too Large 발생시

요청 데이터가 수백바이트 이상으로 큰 경우 발생할 수 있다.

server 항목에 다음과 같이 설정시 어지간하면 해결된다.

```nginx
server {
    client_max_body_size 20M;
}
```