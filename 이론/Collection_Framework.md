# 컬렉션 프레임워크란
- Java Collections Framework라고 불리워지는 Collections API는 Java2 부터 추가 된 자료구조 클래스 패키지를 의미한다.
- 자료(Data)를 다룰 때 반드시 필요한 클래스의 모음으로서 JAVA프로그래머라면 꼭 숙지



![collectionFrameWork](https://user-images.githubusercontent.com/101091478/218373127-951fa8c1-41b5-4730-962e-9af872f28a9e.png)

# Collection = 바구니(어떠한 것들을 집어 넣는다) -> Iterator를 참조
- add(Objct) -> 추가
- size() -> 사이즈
- iterator(): iterator -> 바구니에 넣은 순서를 잘 모르기 때문에 어떠한것이 있으면 꺼낸다라는 느낌
- 꺼낼것이 있는지 없는지부터 판단 -> iterator() 인터페이스로 판단

# Iterator(디자인 패턴의 이름이기도 하다)
hasNext(): boolean -> 참 거짓으로 있는지 없는지
next(): Object -> 하나 꺼내라라는 판단

# List(Collection을 상속받는다)
- get(int): Object  --> int가 순서를 받아드리는 것
- 객체를 담아두기 위한 인터페이스
- 순서를 기억하는 자료구조
- 몇번째 추가되었는지 알 수 있다.

# Set(Collection을 상속받는다)
- add(Object): boolean
- 중복을 허용하지 않겠다라는 자료구조
- 같은값은 한건만 저장

# Map(Key와 Value를 가지고 있다) -> Set을 참조한다
- get(Object): Object   -> 꺼낼 때 사용한다 Object에는 Key값이 들어간다
- keySet(): Set  -> key들값의 집합
- put(Object, Object): void -> (key, 값) == (학번, 이름)
- ex) 학번 -> 학번은 그 사람만 가지고있는 유일한 값 = Key


# ArrayList -> List를 참조
- add(Object) : boolean
- get(int): Object
- iterator(): iterator
- size(): int

# HashSet -> Set을 참조
- add(Object): boolean
- iterator(): Iterator
- size(): int

# HashMap -> Map을 참조
- get(Object): Object
- leuSet() : Set
- put(Object object): void

# java.util.Collection 인터페이스
- java.util.Collection 인터페이스는 컬렉션 프레임워크에서 가장 기본이 되는 인터페이스이다.
- 해당 인터페이슨느 순서를 기억하지 않고, 중복을 허용하여 자료를 다루는 목적으로 만들어졌다.

# java.util.List 인터페이스
- java.util.List 인터페이스는 순서가 중요한 자료를 다룰 때 사용하는 인터페이스이다
- Collection을 상속받음으로써 Collection이 가지고 있는 add(),size(),iterator()메소드를 사용할 수 있다.
- 해당 인터페이스는 순서를 알고 있다고 가정하기 때문에 특정 순서로 저장된 자료를 꺼낼 수 있는 get(int)메소드를 가지고 있다.

# java.util.Set 인터페이스
- java.util.Set 인터페이스는 중복을 허용하지 않는 자료를 다룰 때 사용하는 인터페이스이다.
- 중복을 허용하지 않는다는 것은 같은 값을 저장할 수 없다는 것이다.
- 같은 값을 여러번 추가하여도 마지막 값 하나만 저장됨을 의미한다
- Set인터페이스에 저장된 객체들은 Object가 가지고 있는 equals()메소드와 hashCode()메소드를 오버라이딩 해야한다.

# java.util.Iterator 인터페이스
- java.util.Iterator 인터페이스는 자료구조에서 자료를 꺼내기 위한 목적으로 사용되는 인터페이스이다.
- Iterator 패턴을 구현하고 있다.

# java.util.Map 인터페이스
- java.util.Map 인터페이스는 키(Key)와 값(Value)를 함께 저장하기 위한 목적으로 만들어진 인터페이스이다.
- 같은 Key값으론 하나의 값만 저장할 수 있다.

# 제네릭을 사용하지 않고 ArrayList사용하기
```java
import java.util.ArrayList;

public class ListExam01{
  public static void main(String[] args){
        //자료구조 객체들은 제네릭을 사용하지 않으면
        //Object타입을 저장한다
        
        ArrayList list = new ArrayList();
        list.add("홍");
        list.add("강");
        list.add("석");

        String str1 = (String)list.get(0); //Object타입을 저장하기 때문에 형변환을 해줘야한다
        String str2 = (String)list.get(1);
        String str3 = (String)list.get(2);

        System.out.println(str1);
        System.out.println(str2);
        System.out.println(str3);
  }
    }
```

# 제네릭을 사용한 ArrayList
```java
import java.util.ArrayList;

public class ListExam01{
  public static void main(String[] args){
        ArrayList<String> list = new ArrayList(); //제네릭 사용
        list.add("홍");
        list.add("강");
        list.add("석");

        String str1 = list.get(0); //제네릭을 통해 String타입으로 해줬기 때문에 형변환을 안해도 된다
        String str2 = list.get(1);
        String str3 = list.get(2);

        System.out.println(str1);
        System.out.println(str2);
        System.out.println(str3);
  }
    }
```

# Example Collection&Iterator
```java
package cl;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

public class ListExam03 {
    public static void main(String[] args) {
        Collection<String> collection = new ArrayList<>(); //List가 Collection을 상속받기 때문에 가능
        // 만들어지는 인스턴스는 ArrayList지만 참조타입이 Collection이기 때문에
        // 부모인 Collection(참조타입)이 가지고 있는 메서드밖에 사용하지 못한다.

        collection.add("kim");
        collection.add("lee");
        collection.add("hong");
        //collection/get(0) ->사용 불가 get()은 ArrayList가 가지고있는 메서드이지 Collection이 가지고 있지 않다

        System.out.println(collection.size()); //사이즈를 보여준다

        //Collection을 꺼내기 위한 방법
        Iterator<String> iter = collection.iterator();
        while(iter.hasNext()){ //hasNext()는 꺼낼것이 있느냐 없느냐
            String str = iter.next();
            System.out.println(str);
        }
    }
}
```

# Example Set
```java
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;

public class SetExam {
    public static void main(String[] args) {
        Set<String> set = new HashSet<>();
        set.add("hello");
        set.add("hi");
        set.add("hong");

        Iterator<String> iter = set.iterator();
        while(iter.hasNext()){
            String str = iter.next();
            System.out.println(str);
        }
    }
}
```


