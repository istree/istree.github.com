---
layout: dev
title: crontab
---
명령어를 설정한 주기로 실행해주는 도구이다.

## 편집

```bash
$ crontab -e
```

## 목록보기

```bash
$ crontab -l
```

## 초기화

```bash
$ crontab -r
```

## 실행주기

```bash
*　　　　　　*　　　　　　*　　　　　　*　　　　　　*
분(0-59)　　시간(0-23)　　일(1-31)　　월(1-12)　　　요일(0-7)
```

요일에서 123456은 월화수목금토 이고 0과 7은 일요일이다.

***** 과 같이 모든 값이 *이면 1분마다 실행한다.

### 반복

매 시간 0분, 20분, 40분에 실행

```bash
0,20,40 * * * *
```

### 범위

매 시간 0분 부터 30분까지 1분마다 실행

```bash
0-30 * * * *
```

### 간격

매 10분마다 실행

```bash
*/10 * * * *
```

## 로깅

매분 마다 test.sh 를 실행하고 로그를 test.log에 덮어쓴다.
```bash
* * * * * /home/test.sh > /home/test.log 2>&1
```

로그가 필요 없는 경우
```bash
* * * * * /home/test.sh > /dev/null 2>&1
```

## 백업

크론탭의 내용을 저장한다.

```bash
crontab -l > /home/crontab.txt
```

매일 11시 50분에 크론탭의 내용을 저장한다.

```bash
50 23 * * * crontab -l > /home/crontab.txt
```


## 참고자료

[리눅스 크론탭(Linux Crontab) 사용법](https://jdm.kr/blog/2)
