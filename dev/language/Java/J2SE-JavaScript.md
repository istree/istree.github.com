---
title: J2SE-JavaScript 
---

## 개요

Java SE 7 버전부터 기본으로 탑재된 JavaScript API 이다. Java 1.7 이상 사용 가능하다.

이전 버전에 탑재된 엔진인 Rhino의 64kb 제약이 없다.

## 예제
```java
ScriptEngineManager sem = new ScriptEngineManager();
ScriptEngine se = sem.getEngineByName("JavaScript");
se.eval("var a = 10;");
se.eval("print(a * a)"); // 100
```

## 참고문서

[Java Scripting Programmer's Guide](https://docs.oracle.com/javase/7/docs/technotes/guides/scripting/programmer_guide/)
