---
layout: dev
title: Jekyll
---

## 개요

ruby 기반의 정적 사이트 저작 도구이다.

jekyll이 제공하는 틀에 따라 markdown으로 문서를 작성하고 명령어로 결과물을 생성한다.

블로그 형태의 post 방식과 계층구조의 page 방식으로 작성할 수 있다.

[jekyll 공식가이드(영어)](https://jekyllrb.com/docs/home/)

[jekyll 공식가이드(한글)](https://jekyllrb-ko.github.io/docs/home/)

## 빠른 시작

### 설치
```
$ gem install jekyll
```

### 사이트 생성
```
$ jekyll new mysite
```

### 디렉토리 이동
```
$ cd mysite
```

### 서버 실행
```
$ jekyll serve
```

### 결과 확인

http://localhost:4000

## 부트스트랩

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

pygments 설치가 안될경우 Development Kit을 설치해야한다. [다음글](/note/dev/language/ruby/) 참고

## Liquid 템플릿

jekyll로 page를 작성시 특별한 제어를 위해 Liquid 템플릿 구문을 사용한다.

[Liquid 공식 사이트](https://shopify.github.io/liquid/)

### 주석 처리

{% raw %}
``` liquid
{% comment %}
 ...
{% endcomment %}
```
{% endraw %}

### 문법 강조
{% raw %}
``` liquid
{% highlight ruby %}
 ...
{% endhighlight %}
```
{% endraw %}

### 텍스트를 있는 그대로 처리

문법 강조 기능에서 Liquid의 태그나 필터 또는 HTML을 그대로 처리해야하는 경우
``` liquid
{{ "{% raw" }} %}
...
{{ "{% endraw" }} %}
```

## 문법 강조

문법 강조(syntax highlight)에 색상을 적용하기 위해 CSS 파일을 설정해주어야 한다.

### CSS 파일 추가
[공식 문서에 언급된 CSS 파일](https://github.com/mojombo/tpw/blob/master/css/syntax.css)을다운받는다.

jekyll 디렉토리 내의 원하는 위치에 복사한다.

### layout 파일에 CSS 연결 추가
CSS를 assets 디렉토리에 추가한 경우

``` liquid
<html>
<head>
 ...
<link href="/assets/syntax.css" rel="stylesheet">
 ...
</head>
<body>
</body>
</html>
```

## 사이드바

현재 문서의 디렉토리에서 index.md를 제외한 모든 페이지의 목록을 출력한다.

{% raw %}
``` liquid
{% for curPage in site.pages %}
{% if curPage.dir == page.dir %}
{% if curPage.name != "index.md" %}
              <li><a title="{{ curPage.title }}" href="{{ curPage.url | prepend: site.baseurl }}">{{ curPage.title }}</a></li>
{% endif %}
{% endif %}
{% endfor %}
```
{% endraw %}

## 함수

include를 사용하여 liquid에서 반복적인 부분에 파라미터를 넘겨서 마치 함수처럼 사용할 수 있다.

{% raw %}
```liquid
{% include your_function.html some_parameter="a value" another_parameter=variable_name %}
```
{% endraw %}

## 참고자료

[Jekyll on macOS](https://jekyllrb.com/docs/installation/macos/#brew)

[Setting up your GitHub Pages site locally with Jekyll](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)

[Using Jekyll _includes as custom liquid functions](http://hamishwillee.github.io/2014/11/13/jekyll-includes-are-functions/)

[Advanced Liquid: Group By](https://www.siteleaf.com/blog/advanced-liquid-group-by/)

[Jekyll Filters](https://blog.webjeda.com/jekyll-filters/)

[Jekyll & Liquid Cheatsheet](https://gist.github.com/magicznyleszek/9803727)

