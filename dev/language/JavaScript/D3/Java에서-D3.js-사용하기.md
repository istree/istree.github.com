---
layout: dev
title: Java에서-D3.js-사용하기
---
## 개요

D3.js는 JavaScript로 작성되어있기 때문에 JavaScript 엔진이 있다면 작동시킬 수 있다. (이하 D3)

## Java의 JavaScript 엔진

Java에는 내장된 JavaScript 엔진이 있고 크게 두가지로 나뉜다.

첫 번째로 모질라 재단의 FireFox에 내장된 JavaScript 엔진인 Rhino라고 불리는 라이브러리가 Java에 내장되어 있다. 다만 한번에 돌릴 수 있는 스크립트 파일 크기가 최대 64kb인 제약 사항이 있어서 큰 파일의 스크립트는 사용이 불가능하다. 패키지는 org.mozilla.javascript.* 이다.

두 번째로 Java 1.7 부터 JDK에 새롭게 추가된 JavaScript 엔진은 더 큰 파일의 스크립트도 동작 시킬 수 있다. 패키지는 javax.script.* 이다.

d3.min.js의 파일 크기는 200kb를 넘어서기 때문에 두 번째 방법을 사용해야 하고 이는 최소 Java 1.7 이상을 필요로 한다.

## D3

[D3 다운로드](https://d3js.org/)

## DOM

D3는 DOM을 캡슐화 하고 있기 때문에 document 객체가 필요하다. 웹 브라우저에는 기본적으로 window나 document 객체가 내장되어 있지만 JavaScript 엔진은 말 그대로 엔진일 뿐이라 document 객체가 제공되지 않는다.

이를 해결하기 위해서는 자체적으로 document 객체를 제공해야 한다. 하지만 직접 만들기는 쉽지 않으므로 JavaScript로 작성된 DOM 구현체인 domino를 사용한다.

## domino

[domino GitHub 저장소](https://github.com/fgnass/domino) 모질라의 dom.js 기반의 서버 사이드 DOM 구현체 라고 소개되어 있다.

Node를 대상으로 작성되어진듯 하지만 JavaScript 이므로 모든 JavaScript 엔진에서 동작이 가능하다. 기타 Node용 구현체도 마찬가지로 응용이 가능하지 않을까 싶다.



## 참고문서

[d3java](https://github.com/tritibo/d3java)



