# Any 키워드

자바에서 문자열의 길이를 얻는 함수는 다음과 같다.

```java
private int getLength(Object obj) {
 if (obj instanceof String) {
 return ((String) obj).length();
 }
 return 0;
}
```

이를 코틀린 코드와 비교해보자.
```kotlin
fun getLength(obj: Any): Int { // Object가 Any로 바뀜
 if (obj is String) {
 return obj.length
 }
 return 0
}
```

이를 좀 더 유용하게 사용할 수 있다.
```kotlin
public class Just{}

fun main(args:Array<String>){
    cases("Hello")
    cases(1)
    cases(System.currentTimeMillis())
    cases(484)
    cases("hello")
}

fun cases(obj: Any) {
 when (obj) {
 1 -> println("One")
 "Hello" -> println("Greeting")
 is Long -> println("Long")
 !is String -> println("Not a string")
 else -> println("Unknown")
 }
}
```
실행결과
```
Greeting
One
Long
Not a string
Unknown
```
[온라인으로  실행하기(kotlin 사이트)]([https://try.kotlinlang.org/#/Examples/Hello,%20world!/Simplest%20version/Simplest%20version.kt])

when은 if의 중첩효과. 추측컨대 switch-case문과 비슷한 것 같다.