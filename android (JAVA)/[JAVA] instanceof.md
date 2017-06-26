# instanceof 연산자
참조변수가 참조하고 있는 인스턴스의 실제 타입을 알아보기 위해 instanceof 연산자를 사용

## 사용방법
>객체명 instanceof 타입(클래스명or인터페이스명)

객체가 해당 타입이면 true를 아니면 false를 리턴한다. 타입에 상위 클래스 객체명에 하위 클래스의 객체일 경우에도 true를 리턴한다. 보통 조건문에 많이 사용된다.


## 주의
타입이 상위클래스도 하위클래스도 아닐경우 에러가 난다. 타입은 해당 객체의 클래스의 상위 클래스 혹은 하위클래스여야 한다.

```java
public class A{}
public class B extends A{}
public class C extends B{}

public class InstanceOfTest{
    public static void main(String[] args){
        A a = new A();
        B b = new B();
        C c = new C();

        if(a instanceof A) //true
            System.out.println("a is A's object");
        if(b instanceof A) //true
            System.out.println("b is A's object");
        if(c instanceof A) //true
            System.out.println("c is A's object");

        if(b instanceof C) // 하위클래스이므로 false
            System.out.println("b is C's object");
        if(b instanceof B) //true
            System.out.println("b is B's object");
    }
}
```

실행 결과
```
a is A's object
b is A's object
c is A's object
b is B's object
```


---
### 참고
[아라비안나이트](http://arabiannight.tistory.com/entry/301) |
[아러의 컴퓨터 대백과](http://arer.tistory.com/52)