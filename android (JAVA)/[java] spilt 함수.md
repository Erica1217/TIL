# spilt()
spilt()는 특정 구분자로 문자열을 잘라주는 함수이다.
예를 들면,

> "꽃,나비,집,나무"

라는 문자열이 있을 때, 이것을 spilt()로 쪼개면
> {꽃,나비,집,나무}

이런 배열로 반환해준다.

코드로 보면 이런 느낌이다.

```java
String str = "꽃,나비,집,나무"
String[] array = str.spilt(',');
```

# spilt()와 특수문자
## 그런데, (로 나누려고 했더니 오류가 난다.
왜일까? 정확한 구문은
```java
restName = restName.split("(")[0];
```
였다. 그래서 검색을 해보았더니, 특수문자는 좀 다르게 써야했나보다.

### 1.[]씌워야 할 것들
```
*  ⇒ [*]
+  ⇒ [+]
$  ⇒ [$]
|  ⇒ [|]
```

### 2. \\를 붙여줘야 하는 것들.
```
( ⇒ \\(
) ⇒ \\)
{ ⇒ \\{
} ⇒ \\}
^ ⇒ \\^
[ ⇒ \\[
] ⇒ \\]
```

### 자바의 특수문자는 \을 쓴다.
```
 " ⇒ \"
```

4. 나머지 부호들은 괜찮은 듯 하다.
확인된 것.
```
! # % & @ ` : ; - . < > , ~ '
```
## 해결
```java
restName = restName.split("\\(")[0];
```
이렇게 써서 해결했다.

# spilt 설명
자바 split보면 설명이

> public String[] split(String regex)
Splits this string around matches of the given regular expression.

이렇게 나와있다. 여기서 regex는 표현식.

# 참고
[링크1](http://gaboon.tistory.com/entry/%EC%9E%90%EB%B0%94-%ED%8A%B9%EC%88%98%EB%AC%B8%EC%9E%90)

[링크2](http://gaboon.tistory.com/entry/자바-특수문자)