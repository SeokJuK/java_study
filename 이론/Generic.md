# Generic 사용 방법
- 클래스 이름 옆에 <>가 존재한다
- 괄호 안에는 제네릭의 타입을 적어주고, 주로T(type), K(Key), V(Value)를 사용한다

```java
class GenericBox<T>{
  private T t;
  
  public void set(T obj){  //자바의 모든 클래스의 부모인 Object형태를 매개변수로 받아준다
    this.t = obj;
  }
  
  public T get(){
    return this.t;
  }
}

public class GenericBoxMain{
  public static void main(String[] args){
    GenericBox<String> genericBox = new GenericBox<>(); // 위에서 GenericBox클래스 객체를 생성해준다
    genericBox.set("kim");
    String str = genericBox.get();
    
    GenericBox<Integer> genericBox1 = new GenericBox<>();
    genericBox1. add(new Integer(5));
    Integer intvalue = genericBox.get(); //int같은경우 객체타입이 아니기때문 Integer형태를 사용해줘야한다
  }
}
```

# 제네릭의 장점
- 정해진 타입만 사용하도록 강제할 수 있다
- 타입을 강제함으로서 컴파일할 때 잘못된 타입의 값이 저장되는 것을 막을 수 있다.

# GenericBox
- T는 제네릭과 관련된 부분이다
- 제네릭은 클래스이름 뒤나, 메소드의 리턴타입 앞에 붙을 수 있다.
- <T> 부분의 T라는 이름의 제네릭 타입을 선언한다는 것을 의미한다
- T는 Type의 약자기 때문에 많이 사용되는 문자이지 꼭 T를 사용할 필요는 없다
