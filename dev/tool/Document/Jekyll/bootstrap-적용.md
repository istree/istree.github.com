---
title: bootstrap 적용
---

bootstrap이 미리 적용된 jekyll-bootstrap 프로젝트가 존재한다.

만약 bootstrap을 사용한다면 직접 템플릿을 수정하는것 보다는 손쉽게 적용할 수 있다.

[jekyll-bootstrap 공식 사이트](http://jekyllbootstrap.com/)

[jekyll-bootstrap git 저장소](https://github.com/plusjade/jekyll-bootstrap/)

### 저장소 복사
```
$ git clone https://github.com/plusjade/jekyll-bootstrap/ mysite
```

### 디렉토리 이동
```
$ cd mysite
```

### 서버 실행
```
$ jekyll serve
```

jekyll-sitamep 의존성 오류 발생시 설치후 재실행 한다.
```
$ gem install jekyll-sitemap
```

pygments 의존성 오류 발생시 설치후 재실행 한다.
```
$ gem install pygments.rb
```

pygments 설치가 안될경우 Development Kit을 설치해야한다. [다음글](/dev/language/ruby/) 참고