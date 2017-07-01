# 안전한 NULL 처리 방법
## java의 NULL처리
```java
public void set(@NotNull String a, @Nullable String b) {
 // Do noting
}
```
null이 아닌 경우에는 @NotNull을 이용하고, null이 가능한 경우에는 @Nullable을 이용해 처리한다.

이것을 코틀린 코드로 바꾸면 다음과 같다.

## kotlin의 NULL처리
```kotlin
fun set(a: String, b: String?) {
// Do noting
}
```

## java와 kotlin null 비교

  @Notnull String a ==> a:String
  @Nullable String a ==> a:String?


## null과 관련된 kotlindml 문법오류
```kotlin
var temp: String = "abc"
temp = null // 문법 오류 발생
```
다음 코드를 문법오류가 나지 않게 하려면 String을 String?으로 바꾸면 된다.

```kotlin
var temp: String? = "abc"
temp = null
```

## kotlin에서 null 처리시 주의사항
> null을 사용하기 위해서는 ?에는 Type을 써야한다.

다음 코드는 오류가 발생하는 코드이다.
```kotlin
var temp = null
temp = "ABC" // Type 오류 발생
``` 

이것을 정상적인 코드로 고치면 다음과 같다.
```kotlin
var temp: String? = null
temp = "ABC"
```

## null 체크하기

다음은 null을 체크하는 자바코드이다.
```java
String temp = null;
int size = -1;
if (temp != null) {
 size = temp.length();
}
```

``` java
String temp = null;
int size = 0;
if (!TextUtils.isEmpty(temp)) {
 size = temp.length();
}
```


다음은 null을 체크하는 코틀린코드이다.
```kotlin
var temp: String? = null
var size = -1
if (temp != null) {
 size = temp.length
}
```
## null 체크 간단표현식

자바코드
```java
String temp = null;
int size = temp != null ? temp.length() : 0;
```

코틀린코드
```kotlin
var temp: String? = null
val size = if (temp != null) temp.length else 0
```

## Kotlin Safe Calls
```kotlin
// null을 포함 할 수 있는 temp var 변수이며, null로 초기화 합니다.
var temp: String? = null
```

```kotlin
// null을 포함 할 수 있는 temp var 변수이며, null로 초기화 합니다.
var temp: String? = null
// 물음표(?.)를 다시 한번 포함합니다.
val size = temp?.length
```

## Safe Calls 함수에서 사용 방법
```kotlin
fun getSize(temp: String?): Int? {
 // temp가 NULL이면 null이 return
 // temp가 NULL이 아니면 length가 return
 return temp?.length
}
```

## Safe Calls의 장점
```java
// 다음과 같이 초기화 되었을 경우
// abc = ABC()
// bbb = BBB()
// ddd = null
if (abc != null && bbb != null && ddd != null) {
 return abc.bbb.ddd.name;
}
return null;
```

if문으로 일일히 null체크를 해줘야하는 불편함이 있다.
하지만 코틀린코드는 일일히 null체크를 할 필요가 없다.

```kotlin
return abc?.bbb?.ddd?.name
```

