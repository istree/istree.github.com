---
title: Rhino(Java)
---

## 개요

J2SE 6 에 내장된 기본 JavaScript 엔진이다.

[프로젝트 홈](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino)

[다운로드](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino/Download_Rhino)

[문서](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino/Documentation)

## 예제
```java
Context cx = Context.enter();
ScriptableObject scope = cx.initStandardObjects();
String script = "var a = 2; a * 10;";
Object result = cx.evaluateString(scope, script, "", 1, null);
System.out.println(cx.toString(result)); // 20
```