## 1. 기초
-----------------------
### JDK와 JRE의 차이점은 무엇입니까?

JDK는 Java 언어를 개발하고 컴파일하는 데 사용됩니다. 따라서 JDK는 Java 개발자에게 필요한 도구들을 포함하고 있습니다. <br/>
JRE는 Java 애플리케이션을 실행하는 데 필요한 실행 환경을 제공합니다. 따라서 JRE는 일반 사용자들이 Java 애플리케이션을 실행하는 데 필요한 요소들을 포함하고 있습니다. <br/>
JRE는 Java 애플리케이션을 실행하는 데 필요한 최소한의 구성 요소만을 포함하고 있기 때문에 개발 도구나 컴파일러는 포함되어 있지 않습니다. <br/>
JDK는 JRE를 생성하는 역할을 수행하며, JRE는 JDK에 포함된 도구들 없이는 Java 애플리케이션을 개발하거나 수정할 수 없습니다. <br/>

-----------------------
### ==와 equals의 차이점은 무엇입니까?

"==" 연산자는 두 개의 객체의 레퍼런스(주소)를 비교합니다.
즉, 두 개의 객체가 메모리에서 동일한 위치를 가리키고 있는지를 확인합니다.
"equals()" 메서드는 두 개의 객체의 내용이 동일한지 비교합니다.
기본적으로 Object 클래스에서 상속받은 "equals()" 메서드는 "==" 연산자와 동일한 결과를 반환하도록 구현되어 있으며, 이는 객체의 레퍼런스(주소)를 비교합니다.
하지만 많은 클래스들은 "equals()" 메서드를 오버라이딩하여 객체의 내용을 비교하도록 재정의합니다. 이 경우에는 두 객체의 내용이 같으면 true를 반환하고, 다르면 false를 반환합니다.

-----------------------
### 두 객체가 동일한 hashCode를 가지면 Equals()가 참이어야 합니다, 그렇죠?

hashCode()와 equals()는 서로 다른 목적을 가지고 있으며, hashCode()가 동일하다고 해서 equals()가 참이 되어야 하는 것은 아닙니다. 
해시 충돌이 발생할 수 있으므로, equals() 메서드를 사용하여 정확히 객체의 내용을 비교해야 합니다.

-----------------------
### 자바에서 final의 기능은 무엇입니까?
불변성, 안정성 등을 목적으로 다양한 요소에 적용된다. <br/>
변수: final 변수는 상수로 취급되며, 값을 한 번 할당하면 변경할 수 없습니다. 즉, 변수에 대한 변경이 금지됩니다. <br/>
메서드: final 메서드는 하위 클래스에서 오버라이딩(재정의)할 수 없는 메서드를 나타냅니다. <br/>
클래스: final 클래스는 상속될 수 없는 클래스를 나타냅니다. 

-----------------------
### 자바에서 Math.round(-1.5)는 무엇을 의미합니까?
Math.round() 메서드는 실수 값을 받아와서 그 값에 가장 가까운 정수로 반올림한 결과를 반환합니다. <br/>
따라서 Math.round(-1.5)는 -1.5를 반올림하여 가장 가까운 정수인 -1을 반환합니다. 

-----------------------
### String은 기본 데이터 타입입니까?
아니요, String은 기본 데이터 타입(primitive type)이 아니라 참조 타입(reference type)입니다. <br/>
String은 참조 타입이므로, 객체를 힙(heap)에 할당하고 그 주소를 스택에 저장합니다. <br/>
Java에서 String은 불변(immutable)입니다. 객체 수정 시 새로운 객체를 생성해야만 합니다.

-----------------------
### 자바에서 문자열을 조작하는 클래스는 무엇이 있습니까? 각 클래스의 차이점은 뭘까요?
String 클래스는 불변(immutable)입니다. 즉, 한번 생성된 String 객체는 변경할 수 없습니다. 
StringBuilder 클래스는 가변(mutable)한 객체입니다. 즉, StringBuilder 객체는 생성 후에도 변경할 수 있습니다.
StringBuffer 클래스도 StringBuilder와 마찬가지로 가변(mutable)한 객체입니다. 
StringBuffer는 StringBuilder와 달리 스레드에 안전(thread-safe)합니다. 여러 스레드 작업 시 StringBuffer가 유리합니다.

-----------------------
### String str ="i"와 String str = new String("i")가 동일합니까?
String str = "i";의 경우, 문자열 리터럴 "i"가 스트링 풀(String pool)이라는 특별한 영역에 저장됩니다. 스트링 풀은 JVM의 힙 메모리에 있는 공간입니다.
String 객체를 다시 만들 경우, JVM은 스트링 풀에 있는 같은 값을 가리키도록 합니다. 이 방법은 메모리를 효율적으로 사용하도록 돕습니다.
String str = new String("i");의 경우, 새로운 String 객체가 힙 메모리에 생성됩니다. 
이렇게 생성된 String 객체는 스트링 풀과 상관없이 항상 새로운 메모리 공간을 차지합니다.

-----------------------
### 문자열을 반전시키는 가장 좋은 방법은 무엇인가요?
StringBuilder의 reverse() 메서드를 사용하는 것입니다.

-----------------------
### 추상 클래스에서 추상 메서드는 필수적인가요?
추상 메서드는 선언만 있고 구현부(body)가 없는 메서드를 의미합니다. 이들은 하위 클래스에서 반드시 구현해야 합니다. 추상 클래스는 이런 추상 메서드를 포함할 수 있지만, 반드시 포함하지 않아도 됩니다.

-----------------------
### 보통의 클래스와 추상 클래스의 차이는 무엇인가요?
일반 클래스는 new 키워드를 사용하여 인스턴스화 할 수 있습니다. 그러나 추상 클래스는 직접 인스턴스화 할 수 없습니다. 추상 클래스는 다른 클래스가 상속받아 사용하는 것을 목적으로 합니다. <br/>
일반 클래스는 추상 메서드를 포함할 수 없습니다. 추상 클래스는 추상 메서드를 포함할 수 있습니다. <br/>
정리하면 일반 클래스는 주로 직접 사용하려는 경우에, 추상 클래스는 코드의 재사용성을 높이고 표준 인터페이스를 제공하려는 경우에 사용됩니다.

-----------------------
### final은 추상 클래스를 수정할 때 사용할 수 있나요?
final은 abstract 클래스나 abstract 메서드에 사용할 수 없습니다. final 클래스는 상속될 수 없기 때문에 abstract를 사용할 수 없습니다. final 메서드는 오버라이드할 수 없기 때문에 abstract 메서드가 될 수 없습니다. 
