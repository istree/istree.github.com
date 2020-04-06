---
title: minimal mistakes
---

## 예제

### 사이트 생성
```bash
jekyll new mysite
```

### 디렉토리 이동
```bash
cd mysite
```

### Gemfile 편집
```bash
source "https://rubygems.org"
gem "github-pages", group: :jekyll_plugins
gem "jekyll-include-cache"
```

### 번들 업데이트
```bash
bundle update
```

### _config.yml 편집
```bash
# theme: minima
remote_theme: mmistakes/minimal-mistakes
plugins:
  - jekyll-include-cache 
```

### 결과 확인
서버 실행
```bash
jekyll serve
```

<http://localhost:4000>

## 검색

_config.yml에 다음 항목 추가

```bash
search: true
```

_posts 처럼 collections가 적용된 페이지만 검색이 동작한다.

만약 dev 디렉토리내에 컨텐츠가 있다면 _dev로 변경하고 colllections와 output을 true로 설정해줘야 작동한다.

_config.yml 편집
```bash
collections:
  dev:
    output: true
``` 

## 문제해결

### Liquid Exception: No repo name found. 발생 시
_config.yml에 다음 항목 추가
```bash
repository: user/reposit
```

### Prepending `bundle exec` to your command may solve this.
앞에 bundle exec를 붙인다.
```bash
bundle exec jekyll serve
```

## 참고자료 

[Minimal Mistakes GitHub 페이지](https://mmistakes.github.io/minimal-mistakes/)

[Minimal Mistakes GitHub 저장소](https://github.com/mmistakes/minimal-mistakes)
