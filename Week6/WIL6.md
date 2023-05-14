# [StudyWIL] Week 6 - Chapter 4

## 추상 클래스와 인터페이스

**추상 메서드**: 선언부는 있지만 구현부는 없는~

**추상 클래스**: 추상 메서드를 하나라도 갖고 있으면 추상 클래스로 선언해야함

```java
public abstract class Animal {
  abstract void cry();
}
```

`Animal Jimseung = new Animal();`

→ Error! Animal 타입은 객체를 만들 수 없다.  
<br>
👉 추상 메서드는 하위 클래스에게 메서드의 구현(오버라이딩)을 강제함.  
<br>

## static과 final 그리고 불변 객체

**static 블록**  
: 클래스가 static 영역에 배치될 때 실행됨!!

```java
public class Animal {
	**static** {
		System.out.println("동물 클래스 ready");
	}
}
```

<br>

**➕ static 변수의 초기화 시점**  
[클래스 로더의 클래스 로드 과정]

1. 로드 : 클래스 파일을 가져와서 JVM의 메모리에 로드
2. 검증 : JAVA Language Specification 및 JVM 명세대로 구성되어 있는지 검사
3. 준비 : 클래스가 필요로 하는 메모리를 할당 (필드, 메서드, 인터페이스 등)
4. 분석 : 클래스의 상수 풀 내 모든 심볼릭 레퍼런스를 다이렉트 레퍼런스로 변경
5. **초기화** : 클래스 변수들을 적절한 겂으로 초기화

<br>

**final 키워드**

final 키워드가 붙은 클래스는 상속을 허락하지 않는다!  
→ 하위 클래스를 만들 수 없다  
<br>
final 키워드가 붙은 변수는 변경을 허락하지 않는다!  
→ 한번 초기화된 변수는 값을 변경할 수 없다  
→ 초기화는 선언 시/static블록 내부 에서 가능하다  
• static으로 선언한 변수 : 객체 생성 시 초기화?  
-> 선언 시에/static 블록 내부에서 가능  
<br>
final 키워드가 붙은 메서드는 오버라이딩을 허락하지 않는다!  
<br>

## instanceof 연산자

만들어진 객체가 특정 클래스의 인스턴스인지 물어보는 연산자  
→ true 나 false 반환

```java
class Animal {
}

class Bird extends Animal {
}

public class Driver {
	public static void main(String[] args) {
		Animal animal1 = new Animal();
		**Bird** bird1 = new Bird();

		System.out.println(bird1 instanceof Animal);  // true
		System.out.println(bird1 instanceof Bird);  // true
	}
}
```

<br>

```java
public class Driver {
	public static void main(String[] args) {
		Animal animal1 = new Animal();
		************Aniaml************ bird1 = new Bird();

		System.out.println(bird1 instanceof Animal);  // true
		System.out.println(bird1 instanceof Bird);  // true
	}
}
```

→ 객체 참조 변수의 타입이 아닌 실제 객체의 타입에 의해 처리하기 때문!
<br>
🧐 instanceof 연산자는 상속관계 뿐만 아니라 인터페이스의 구현 관계에서도 동일하게 작용

```java
interface CanFly {
}

class Parrot implements CanFly {
}

public class Driver {
	public static void main(String[] args) {
		CanFly parrot1 = new Parrot();

		System.out.println(parrot1 instanceof CanFly);  // true
		System.out.println(parrot1 instanceof Parrot);  // true
	}
}
```

<br>
