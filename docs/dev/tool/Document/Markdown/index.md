---
title: Markdown
---

## 기본 문법

### 머리말

샵(&#35;)을 반복적으로 입력한다. H1 부터 H6까지 있다.

```markdown
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

### 개행

문장의 마지막에 공백을 2개 입력하면 한줄 개행  
Enter를 두번 입력하면 두줄 개행된다.

```markdown
공백 2개 입력  
한줄 개행

Enter 두번 입력

두줄 개행
```
### 굵게

```markdown
**강조**
```

### 기울임

```markdown
*강조*
```

### 인용

들여쓰기로 강조한다.

```markdown
> 인용1
>> 인용2
>>> 인용3
```

### 순차 목록(Ordered List)

앞에 번호가 붙는 목록

```markdown
1. 첫째줄
2. 둘째줄
3. 셋째줄
```

### 비순차 목록(Unordered List)

앞에 점이 붙는 목록

```markdown
- 첫째줄 
- 둘째줄 
- 셋째줄
```
### 코드

```markdown
`코드`
```

### 구분선

```markdown
---
```

### 링크

```markdown
[이름](http://주소)
```

### 이미지

```markdown
![이름](image.jpg)
```

## 확장 문법

### 표

```markdown
| 열1 | 열2 |
| --- | --- |
| 행1 | 내용1 |
| 행2 | 내용2 |
```

### 코드 블록

~~~
```markdown
int main() {
    printf("hello world");
}
```
~~~

### 각주

```markdown
각주를 사용합니다. [^1]

[^1]: 각주 내용.
```

### 머릿말 ID

```markdown
### 머릿말 {#id}
[머릿말로 이동](#id)
```

### 정의 목록

```markdown
용어
: 정의1
: 정의2
```

### 취소선

```markdown
~~취소선 내용~~
```

### 작업 목록

```markdown
- [x] 작업1
- [ ] 작업2
- [ ] 작업3
```

### 참고자료

[Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)

[마크다운 표만들기](https://steemit.com/kr/@antares007/-201787t14245290z)

[Escape Markdown Fenced Code Blocks](https://markdownmonster.west-wind.com/docs/_5eg1brc0z.htm)