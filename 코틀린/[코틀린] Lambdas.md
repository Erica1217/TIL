# Lanbdas
```java
button.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 view.setAlpha(0.5f);
 }
});
```
버튼에 클릭리스너를 주는 코드이다. 이것을 코틀린식으로 바꾸면

```kotlin
button.setOnClickListener {
 view -> view.alpha = 0.5f
}
```

이렇게 훨씬 간결하게 줄일 수 있다.
하지만 이것보다 더 간결하게 줄일 수 있다.

```kotlin
button.setOnClickListener {
 it.alpha = 0.5f
}
```
**it**이라는 키워드를 사용한 것이다.
it 키워드는 
>View view

이렇게 키워드가 한개일때만 사용가능하다.
변수가 여러개일 경우, 
>view -> view.alpha = 0.5f

이 형식을 따라야한다.