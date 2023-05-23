### JDK와 JRE의 차이점은 무엇입니까?

JDK는 Java 언어를 개발하고 컴파일하는 데 사용됩니다. 따라서 JDK는 Java 개발자에게 필요한 도구들을 포함하고 있습니다.
JRE는 Java 애플리케이션을 실행하는 데 필요한 실행 환경을 제공합니다. 따라서 JRE는 일반 사용자들이 Java 애플리케이션을 실행하는 데 필요한 요소들을 포함하고 있습니다.
JRE는 Java 애플리케이션을 실행하는 데 필요한 최소한의 구성 요소만을 포함하고 있기 때문에 개발 도구나 컴파일러는 포함되어 있지 않습니다.
JDK는 JRE를 생성하는 역할을 수행하며, JRE는 JDK에 포함된 도구들 없이는 Java 애플리케이션을 개발하거나 수정할 수 없습니다.

### ==와 equals의 차이점은 무엇입니까?

"==" 연산자는 두 개의 객체의 레퍼런스(주소)를 비교합니다.
즉, 두 개의 객체가 메모리에서 동일한 위치를 가리키고 있는지를 확인합니다.
"equals()" 메서드는 두 개의 객체의 내용이 동일한지 비교합니다.
기본적으로 Object 클래스에서 상속받은 "equals()" 메서드는 "==" 연산자와 동일한 결과를 반환하도록 구현되어 있으며, 이는 객체의 레퍼런스(주소)를 비교합니다.
하지만 많은 클래스들은 "equals()" 메서드를 오버라이딩하여 객체의 내용을 비교하도록 재정의합니다. 이 경우에는 두 객체의 내용이 같으면 true를 반환하고, 다르면 false를 반환합니다.

### 두 객체가 동일한 hashCode를 가지면 Equals()가 참이어야 합니다, 그렇죠?

hashCode()와 equals()는 서로 다른 목적을 가지고 있으며, hashCode()가 동일하다고 해서 equals()가 참이 되어야 하는 것은 아닙니다. 
해시 충돌이 발생할 수 있으므로, equals() 메서드를 사용하여 정확히 객체의 내용을 비교해야 합니다.

