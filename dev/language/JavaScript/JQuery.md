---
title: JQuery
---
## jQuery.when 에서 배열 사용

여러개의 url 응답이 모두 완료된 후 뭔가를 실행해야 할 경우 when과 함께 Deferred Object를 사용한다.

예를 들어 두개의 url의 응답을 받아 결과를 출력하려면 다음과 같다.

```javascript
jQuery.when( 
    jQuery.get('a.txt'), 
    jQuery.get('b.txt') 
).done( function(a,b) {
    console.log(a);
    console.log(b);
});
```

다만 when의 파라미터는 고정되어 있고 배열을 처리해주지 않는다.

요청할 url이 여러개일 경우 배열로 처리하고 싶다면? 아래와 같이 할 수 있다.

```javascript
var acts = urls.map(function(url) {
    return jQuery.get(url);
});

jQuery.when.apply(
    jQuery,
    acts
).done(function() {
    var results = Array.prototype.slice.call(arguments);
    results.map(function(result) {
        console.log(result[0]);
    });
});
```

관련글 <https://stackoverflow.com/questions/5627284/pass-in-an-array-of-deferreds-to-when>


## 참고자료

[Ajax/jQuery.getJSON Simple Example](https://www.sitepoint.com/ajaxjquery-getjson-simple-example/)