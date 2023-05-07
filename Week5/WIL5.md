# [StudyWIL] Week 5 - Chapter 3

## 객체지향 패러다임과 객체란?

객체: 세상에 존재하는 유일무이한 사물  
클래스: 분류 또는 집합. 같은 속성과 기능을 가진 객체를 총칭하는 개념. 추상화의 결과.
<br>
**클래스와 객체의 관계**  
클래스 : 객체 = 사람 : 찰푸 = 펭귄 : 뽀로로 = 쥐 : 미키마우스

## 객체 지향의 4대 특성

캡! 상추다 로 외우라고 하네요...  
<br>
캡슐화(Encapsulation) : 정보 은닉  
상속(~~Inheritance~~) : 재사용  
추상화(Abstraction) : 모델링! 구체적인 것을 분해해서 관심 영역, Application Boudary에 있는 특성만 가지고 재조합하는 것.  
다형성(Polymorphism) : 사용 편의

## 추상화와 T 메모리

추상화의 결과물 모델은 자바에서 클래스로 표현.  
클래스 모델의 표현하는 국제 표준 표기법 : UML 클래스 다이어그램

```java
Mouse mickey = new Mouse();
```

: 참조변수 mickey에 Mouse 객체의 주소(포인터) 할당
<br>
클래스 멤버와 객체 멤버를 구분하는 키워드 : **static**
<br>
객체의 속성 중 모든 객체에서 같은 값인 속성에 대해 메모리 할당을 한 번만 하는 법 : **static**  
→ 그럼 클래스 멤버 속성이 되고, heap이 아닌 static 영역에 할당됨  
ClassName.countOfTail 과 같이 클래스명.속성명 으로도 접근 가능
<br>
💡 main() 메서드는 항상 static이 붙음 → 클래스 멤버 메서드니까
<br>
상속의 is a 관계?  
→ is a 대신에 is a kind of 로 생각하자!  
→ 하위클래스 is a kind of 상위클래스

## 오버라이딩 vs 오버로딩

오버라이딩:  
맨 위에 올라탄 존재만 보인다  
(재정의한 이후의 메소드만 보인다)  
<br>
오버로딩:  
옆으로 적재된 모든 물체가 다 보인다
<br>
💡 상위클래스 타입의 객체 참조 변수를 사용하더라도 하위클래스에서 오버라이딩(재정의)한 메소드가 호출됨!!

```java
Animal pingu = new Penguin();
```

처럼 pingu는 Animal 인스턴스를 가리키지만, Penguin에서 재정의한 메소드가 호출된다.

## call by value 와 call by reference

Call By Value로 한 변수 복사와 Call By Reference로 한 참조변수 복사 모두 해당 변수가 가진 값이 그대로 복사된다.  
근데 이제 Call By Value는 그 값을 값 자체로 해석하고,  
Call By Reference는 그 값을 주소로 해석하는 것이다.
