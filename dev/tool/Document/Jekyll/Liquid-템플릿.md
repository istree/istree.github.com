---
title: Liquid 템플릿
---
jekyll로 page를 작성시 특별한 제어를 위해 Liquid 템플릿 구문을 사용한다.

[Liquid 공식 사이트](https://shopify.github.io/liquid/)

## 주석 처리

{% raw %}
``` liquid
{% comment %}
 ...
{% endcomment %}
```
{% endraw %}

## 문법 강조
{% raw %}
``` liquid
{% highlight ruby %}
 ...
{% endhighlight %}
```
{% endraw %}

## 텍스트를 있는 그대로 처리

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

[Using Jekyll _includes as custom liquid functions](http://hamishwillee.github.io/2014/11/13/jekyll-includes-are-functions/)

[Advanced Liquid: Group By](https://www.siteleaf.com/blog/advanced-liquid-group-by/)

[Jekyll Filters](https://blog.webjeda.com/jekyll-filters/)

[Jekyll & Liquid Cheatsheet](https://gist.github.com/magicznyleszek/9803727)