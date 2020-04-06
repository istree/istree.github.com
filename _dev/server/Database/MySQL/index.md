---
title: MySQL
---
## 로그인

```bash
$ mysql -u root -p
```

## 사용자 추가

```sql
> create user '사용자'@'localhost' identified by '비밀번호';
```

## 권한 부여

```sql
> grant all privileges on DB이름.* to '사용자'@'localhost';
```

모든 IP에서 접근을 허용할 시 localhost 대신 %를 사용한다.


## 사용자 계정 삭제

```sql
> drop user '사용자'@'localhost';
```

