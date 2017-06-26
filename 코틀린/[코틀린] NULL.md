# null
```kotlin
var a: Int = 123
a = null //ERROR!
```
코틀린에선 non-null을 지향하기때문에 모든변수에 그냥 null을 집어넣으면 에러가 난다. 

# null 사용하고 싶니?
그럴땐 타입옆에 '?'를 붙혀주면 된다.

```kotlin
var a: Int? = 123
a = null //OK!
```
