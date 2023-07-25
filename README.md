## 1. 자바 기초
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

-----------------------
## 2. Container
-----------------------
### 컨테이너란 무엇인가요?
컨테이너는 특정 객체의 생성과 관리를 담당하여 객체 운용에 필요한 다양한 기능을 제공합니다.

-----------------------
### Collection과 Collections의 차이는 무엇인가요?
Collection은 Java에서 여러 값을 담을 수 있는 객체, 즉 컬렉션을 위한 최상위 인터페이스입니다. List, Set, Queue 등의 컬렉션 인터페이스는 모두 Collection 인터페이스를 상속받습니다.
Collections는 이런 컬렉션을 조작하는 데 도움이 되는 메서드들을 제공하는 클래스입니다. ex) Collections.sort() 

-----------------------
### List, Set, Map의 차이점을 말해주세요.
List는 순서가 있는 컬렉션입니다. List는 중복된 요소를 허용하며 요소의 위치를 기반으로 접근할 수 있습니다. 
Set은 순서를 유지하지 않는 컬렉션입니다. 가장 큰 특징은 중복된 요소를 허용하지 않는다는 것입니다. 
Map은 키와 값의 쌍을 저장하는 데이터 구조입니다. 각 키는 고유하므로 중복을 허용하지 않으며, 각 키는 하나의 값을 가리킵니다.

-----------------------
### HashMap과 Hashtable의 차이는 무엇인가요?
HashMap과 Hashtable은 둘 다 Java에서 사용되는 Map 인터페이스를 구현하는 클래스입니다.
(동기화) HashMap은 동기화되어 있지 않아 기본적으로 스레드 안전하지 않습니다. 
Hashtable은 동기화되어 있어 여러 스레드가 동시에 접근하더라도 스레드 안전성을 보장합니다. 
(Null 허용) HashMap은 null 키와 null 값을 허용합니다. Hashtable은 null 키나 null 값을 허용하지 않습니다. 
(성능) HashMap이 Hashtable보다 일반적으로 빠른 성능을 보입니다. 이는 Hashtable이 동기화를 위한 추가적인 오버헤드를 가지고 있기 때문입니다.

-----------------------
### 각각 어떤 상황에서 HashMap과 TreeMap을 선택하나요?
HashMap은 해시 테이블을 사용하여 요소를 저장합니다. 이로 인해 HashMap의 주요 연산(삽입, 삭제, 탐색)의 시간 복잡도는 일반적으로 O(1)입니다. HashMap은 요소의 삽입 순서를 유지하지 않습니다. 
TreeMap은 균형 이진 검색 트리를 사용하여 요소를 저장합니다. 이로 인해 TreeMap의 주요 연산(삽입, 삭제, 탐색)의 시간 복잡도는 O(log n)입니다. 키는 순서대로 정렬됩니다.

-----------------------
### HashMap 구현 원칙은 무엇인가요?
HashMap은 키 객체의 hashCode() 메서드를 사용하여 해시코드를 생성하고, 이를 이용하여 키-값 쌍을 저장하거나 검색합니다. 
HashMap은 내부적으로 버킷 배열을 사용합니다. 각 버킷은 키-값 쌍을 저장하는 엔트리의 연결 리스트를 참조할 수 있습니다. 
키의 해시코드는 버킷 배열의 인덱스로 변환되어, 해당 키-값 쌍이 저장될 위치를 결정합니다.

-----------------------
### ArrayList와 LinkedList의 차이점은 무엇인가요?
(내부 데이터 구조) ArrayList는 내부적으로 동적 배열을 사용하여 데이터를 저장합니다. 반면에 LinkedList는 이중 연결 리스트를 사용하여 데이터를 저장합니다.
(메모리 사용) ArrayList는 요소의 데이터만 저장하는 반면, LinkedList는 요소의 데이터와 함께 다음 및 이전 노드에 대한 두 개의 참조를 저장해야 하므로 더 많은 메모리를 사용합니다.
(탐색 및 액세스 성능) ArrayList는 인덱스를 기반으로 요소에 직접 접근할 수 있으므로, 요소의 탐색 및 액세스에는 O(1)의 시간 복잡도가 필요합니다. 반면에 LinkedList는 요소의 액세스가 순차적이므로, 리스트의 요소에 접근하는 데 O(n)의 시간 복잡도가 필요합니다.
(삽입 및 삭제 성능) ArrayList는 요소가 삽입되거나 삭제될 때 배열의 크기를 조정해야 하므로, 이 연산에는 O(n)의 시간 복잡도가 필요합니다. 반면에 LinkedList는 양방향 연결 리스트이므로, 리스트의 시작이나 끝에서의 요소의 삽입 및 삭제는 O(1)의 시간 복잡도를 가집니다. 하지만 이는 인덱스가 알려진 경우의 이야기이고, 인덱스가 알려지지 않은 상태에서 LinkedList에서 요소를 찾는 데는 O(n)의 시간이 소요됩니다.

-----------------------
### Array에서 List로 전환하려면 어떻게 해야하나요?
Java에서 배열을 리스트로 전환하는 것은 Arrays 클래스의 asList() 메소드를 사용하여 쉽게 할 수 있습니다.
List<String> list = Arrays.asList(array);
이 변환된 리스트는 고정 크기를 가지므로, ArrayList 생성자를 사용하여 새 ArrayList를 생성하는 것이 좋습니다.
List<String> list = new ArrayList<>(Arrays.asList(array));

-----------------------
### Array와 ArrayList의 차이점을 말해주세요.
Array는 고정된 크기를 가지고, ArrayList는 동적으로 크기가 조정될 수 있는 가변 크기 배열입니다.
Array는 원시 타입과 객체 모두를 저장할 수 있습니다. 
반면에 ArrayList는 객체만을 저장할 수 있으며, 원시 타입은 래퍼 클래스를 통해 객체로 변환되어야 합니다.

-----------------------
### Queue에서, poll()과 remove()의 차이는 무엇인가요?
poll() 메소드는 큐에서 가장 앞에 있는 요소를 제거하고 그 요소를 반환합니다. 만약 큐가 비어있다면 null을 반환합니다.
remove() 메소드도 큐에서 가장 앞에 있는 요소를 제거하고 그 요소를 반환합니다. 그러나 큐가 비어있을 때 remove() 메소드를 호출하면, poll() 메소드와는 달리 NoSuchElementException을 던집니다.

-----------------------
### thread-safe한 컬렉션 클래스들은 무엇이 있을까요?
ConcurrentHashMap, CopyOnWriteArrayList, CopyOnWriteArraySet, ConcurrentLinkedQueue, ConcurrentLinkedDeque 등이 있습니다.

-----------------------
### iterator란 무엇인가요?
Iterator는 Java의 Collection Framework에서 데이터 요소를 순차적으로 접근하는데 사용되는 인터페이스입니다.

-----------------------
### iterator의 사용 목적은 무엇인가요? 어떤 특징이 있죠?
Iterator를 사용하면 컬렉션의 요소를 순회하는 동안 해당 요소를 안전하게 제거할 수 있습니다. next() 메서드는 순회할 다음 요소를 반환하고, hasNext() 메서드는 순회할 요소가 더 있는지를 확인하고, remove() 메서드는 next() 메서드로 반환된 마지막 요소를 컬렉션에서 제거하는 기능을 제공합니다. 일반적으로 hasNext(), next(), remove() 순으로 메소드를 호출해야 한다.

-----------------------
### iterator와 listIterator의 차이는 무엇인가요?
Iterator는 전진 방향으로만 요소를 순회할 수 있습니다. 반면에 ListIterator는 양방향으로 순회할 수 있습니다. 
ListIterator는 add(E e)와 set(E e)라는 메서드를 제공하여 리스트의 요소를 추가하거나 수정할 수 있습니다. 
반면에 Iterator는 요소를 제거하는 remove() 메서드만 제공하며, 요소를 추가하거나 수정하는 기능은 제공하지 않습니다.

-----------------------
## 3. multi-threading
-----------------------
### 병렬과 동시성의 차이점을 말해주세요.
병렬성은 '실제로 동시에 여러 작업을 처리하는 것'이고(여러 개의 CPU), 동시성은 '한 번에 하나의 작업을 처리하지만, 여러 작업이 동시에 실행되는 것처럼 보이게 하는 것'(한 개의 CPU)입니다.

-----------------------
### 프로세스와 스레드의 차이를 말해주세요.
프로세스는 실행 중인 프로그램의 인스턴스이며, 스레드는 프로세스 내에서 실행되는 가장 작은 실행 단위입니다. 
프로세스는 독립적이며 격리된 반면, 스레드는 자원을 공유하므로 상호작용하기가 더 쉽습니다. 하지만 이런 특성 때문에 동시성 제어가 필요하게 됩니다.

-----------------------
### 데몬 스레드는 무엇인가요?
데몬 스레드는 주 스레드의 작업을 돕는 보조적인 역할을 하는 스레드입니다. 일반적으로 백그라운드에서 실행되어 다른 일반(또는 사용자) 스레드의 동작을 지원합니다.

-----------------------
### 스레드를 만드는 방법을 나열해주세요.
1. Thread 클래스를 확장하는 클래스를 만들고, 그 클래스의 run 메서드를 재정의(오버라이드)합니다. 그런 다음, 그 클래스의 인스턴스를 만들고, start 메서드를 호출하여 스레드를 시작합니다.
2. Runnable 인터페이스를 구현하는 클래스를 만듭니다. 이 인터페이스는 run이라는 단일 메서드만 정의하고 있습니다. Runnable 객체는 Thread 객체에 전달되어 스레드가 시작될 때 실행됩니다.

-----------------------
### runnable과 callable의 차이는 무엇인가요?
Runnable과 Callable은 둘 다 자바에서 별도의 스레드에서 실행되는 작업을 정의하는 인터페이스입니다.
Callable은 Runnable의 확장된 형태로서 결과를 반환할 수 있고 예외를 던질 수 있습니다.

-----------------------
### 스레드의 여러가지 상태에 대해 말해주세요.
New (신규): 스레드가 생성되었지만 아직 시작되지 않은 상태입니다.
Runnable (실행 가능): 스레드가 실행 중이거나 실행을 위해 준비된 상태입니다. 
Blocked (차단됨): 스레드가 기다리는 동안 차단된 상태입니다.
Waiting (대기 중): 스레드가 다른 스레드에 의해 신호를 받을 때까지 무한히 기다리는 상태입니다.
Timed Waiting (시간 제한 대기 중): 스레드가 지정된 시간 동안 기다리는 상태입니다.
Terminated (종료됨): 스레드가 작업을 모두 완료하거나 예외적인 방법으로 종료된 상태입니다.

-----------------------
### sleep()과 wait()의 차이는 무엇인가요?
sleep()은 주어진 시간 동안 스레드를 일시 중지하며 락을 유지하는 반면, wait()은 다른 스레드로부터 신호를 받거나 지정된 시간이 경과할 때까지 스레드를 중지하며 락을 해제합니다.

-----------------------
### notify()와 notifyAll()의 차이는 무엇인가요?
notify()는 wait()로 인해 일시 정지된 스레드 중 하나만 깨웁니다. notifyAll()는 wait()로 인해 일시 정지된 모든 스레드를 깨웁니다.

-----------------------
### thread run()과 thread start()의 차이는 무엇인가요?
run() 메서드는 Thread 클래스가 구현하는 Runnable 인터페이스의 메서드입니다. run() 메서드 내부에는 스레드가 수행해야 하는 작업을 정의합니다. 
start() 메서드는 새로운 스레드를 생성하고, 그 스레드에서 run() 메서드를 호출합니다. 

-----------------------
### 스레드 풀을 생성할 수 있는 여러가지 방법을 말해주세요.
newFixedThreadPool(int nThreads): 고정된 크기의 스레드 풀을 생성합니다. 이 풀의 스레드 수는 변경되지 않으며, 모든 스레드가 동시에 작업을 수행하도록 할 수 있습니다.

newCachedThreadPool(): 캐시된 스레드 풀을 생성합니다. 이 풀은 필요에 따라 스레드 수를 자동으로 조정하며, 사용하지 않는 스레드는 일정 시간이 지나면 자동으로 제거합니다.

newSingleThreadExecutor(): 하나의 스레드만을 가진 스레드 풀을 생성합니다. 이 풀은 한 번에 하나의 작업만 수행할 수 있으며, 특정 작업이 순차적으로 실행되어야 할 때 유용합니다.

newScheduledThreadPool(int corePoolSize): 주어진 수의 스레드를 가진 스레드 풀을 생성합니다. 이 풀은 스레드에 대해 예약된 작업을 수행할 수 있습니다. 즉, 일정 시간이 지난 후에나 주기적으로 작업을 수행하도록 스레드를 예약할 수 있습니다.

newWorkStealingPool(int parallelism): 주어진 병렬성 수준에 따라 스레드 수를 조정하는 스레드 풀을 생성합니다. 이 풀은 자바 8에서 추가되었으며, Fork/Join 프레임워크에 기반한 병렬 작업 처리를 지원합니다.

-----------------------
### 스레드 풀의 상태에 대해 말해주세요.
Running: 스레드 풀이 작업을 수락하고 처리하는 상태입니다. 스레드 풀이 생성되자마자 기본적으로 이 상태로 시작됩니다.

Shutting down: shutdown() 메서드가 호출되면 스레드 풀이 이 상태로 전환됩니다. 이 상태에서는 기존 작업은 계속 처리되지만 새로운 작업은 수락되지 않습니다.

Terminated: 모든 작업이 완료되고 모든 스레드가 종료되면 스레드 풀이 이 상태로 전환됩니다.

Stop: shutdownNow() 메서드가 호출되면 스레드 풀이 이 상태로 전환됩니다. 이 상태에서는 실행 중인 모든 작업이 중단되고, 대기 중인 모든 작업이 폐기되며, 새로운 작업은 수락되지 않습니다. 이 상태를 직접 확인할 수 있는 메서드는 제공되지 않지만, isTerminated() 메서드를 통해 스레드 풀이 종료된 상태인지 확인할 수 있습니다.

-----------------------
### 스레드 풀에서 submit()과 execute()의 차이는 무엇인가요?
submit() 메서드와 execute() 메서드는 ExecutorService 인터페이스에서 제공하는 두 가지 방법으로 작업을 스레드 풀에 제출하는 방법입니다. 
작업의 결과를 받아야 하거나 작업의 상태를 관리해야 하는 경우 submit() 메서드를 사용하고, 그렇지 않은 경우 execute() 메서드를 사용하는 것이 일반적입니다.

-----------------------
### 자바 프로그램에서 멀티 스레드 작업의 안전성을 어떻게 보장할 수 있을까요?
동기화(Synchronization): 자바에서는 synchronized 키워드를 사용하여 특정 메서드나 블록에 한 번에 하나의 스레드만 접근하도록 할 수 있습니다. 이는 race condition이라는 상황을 피하기 위해 사용됩니다.

변수의 Volatile 선언: volatile 키워드를 사용하여 변수를 선언하면, 해당 변수는 메인 메모리에서 직접 읽고 쓰게 되므로 여러 스레드가 해당 변수를 동시에 읽거나 쓰는 것을 방지할 수 있습니다.

Atomic 클래스 사용: 자바의 java.util.concurrent.atomic 패키지에는 Atomic 클래스들이 있습니다. 이 클래스들은 원자성을 보장하는 연산을 제공합니다. 예를 들어, AtomicInteger 클래스는 원자적으로 증가 또는 감소시키는 메서드를 제공합니다.

Lock 인터페이스: java.util.concurrent.locks 패키지의 Lock 인터페이스는 더 세밀한 잠금을 제공합니다. synchronized 블록과 달리, Lock 인터페이스를 사용하면 시간 제한을 두고 잠금을 시도하거나, 인터럽트가 가능한 잠금을 시도하거나, 공정성(fairness)을 통한 잠금 순서를 보장할 수 있습니다.

Thread-safe Collections: Java는 자체적으로 thread-safe collection 클래스를 제공합니다. 예를 들어, Vector, Hashtable, ConcurrentHashMap, CopyOnWriteArrayList 등은 멀티스레드 환경에서도 안전하게 사용할 수 있는 컬렉션들입니다.

Immutable Objects: Immutable 객체는 한 번 생성되면 상태를 변경할 수 없는 객체를 말합니다. 따라서, 여러 스레드에서 동시에 접근해도 데이터 일관성에 문제가 없습니다.

-----------------------
## 4. reflection
-----------------------
### reflection이란 무엇인가요?
리플렉션(Reflection)은 자바에서 제공하는 API로, 런타임에 클래스, 인터페이스, 메서드 및 변수와 같은 객체의 내부 정보를 검사하거나 조작하는 기능을 제공합니다.

-----------------------
### 자바 직렬화란 무엇인가요? 
자바 직렬화(Java Serialization)는 자바 객체를 바이트 스트림으로 변환하는 과정을 말합니다. 
이 변환 과정을 통해 객체의 상태를 저장하거나 네트워크를 통해 전송할 수 있습니다. 
자바에서는 Serializable 인터페이스를 구현하여 클래스를 직렬화 가능하게 만듭니다. 
직렬화된 객체는 파일 시스템에 저장하거나 메모리에 보관할 수 있으며, 나중에 다시 객체로 역직렬화(Deserialization)하여 사용할 수 있습니다.

-----------------------
### 자바 직렬화는 어떤 상황에서 필요한가요?
영속성(Persistence): 객체의 상태를 파일 시스템이나 데이터베이스 등에 저장하고, 나중에 필요할 때 다시 복원하기 위해 직렬화를 사용합니다. 이를 통해 데이터를 영속적으로 저장하고 관리할 수 있습니다.
원격 메소드 호출(Remote Method Invocation, RMI): 네트워크를 통해 객체를 전송하거나 메소드를 호출할 때는 객체를 바이트 스트림으로 변환해야 합니다. 이 경우에도 직렬화를 활용합니다.
분산 컴퓨팅(Distributed Computing): 분산 시스템에서는 여러 컴퓨터에 분산되어 실행되는 객체들 사이에 데이터를 전송해야 할 필요가 있습니다. 이때 직렬화를 사용하여 객체를 바이트 스트림으로 변환하고, 다른 컴퓨터에서 이 스트림을 다시 객체로 역직렬화할 수 있습니다.

-----------------------
### 동적 프록시란 무엇인가요?
동적 프록시는 실행 시점에 프록시 객체를 생성하는 방법을 가리킵니다. java.lang.reflect.Proxy 클래스를 이용하여 동적 프록시를 생성할 수 있습니다. 

-----------------------
## 5. object copy
-----------------------
### 복사가 사용되는 이유는 무엇인가요? 
원본 데이터를 보호하기 위해 복사본을 만들어 사용하는 경우가 많습니다. 그리고 복사본을 만들어서 별도의 작업을 수행하면 원본 데이터에 영향을 주지 않고 독립적으로 작업을 수행할 수 있습니다.

-----------------------
### 깊은 복사와 얕은 복사의 차이를 말해주세요.
얕은 복사(Shallow Copy)는 객체를 복사할 때, 객체 내부의 필드는 동일한 참조값을 가지게 됩니다.
깊은 복사(Deep Copy)는 객체를 복사할 때, 객체 내부의 필드까지 새롭게 복사를 하게 됩니다. 
얕은 복사는 메모리와 시간 효율성이 뛰어나지만, 원본 객체와 복사본이 동일한 데이터를 참조하므로 데이터의 독립성이 없습니다. 
반면에 깊은 복사는 메모리와 시간 비용이 더 들지만, 데이터의 독립성을 보장합니다.

-----------------------
## 6. Java Web
-----------------------
### jsp와 servlet의 차이점은 무엇인가요?
JSP와 Servlet는 모두 Java 기반의 웹 컴포넌트로서 HTTP 요청에 대해 동적인 웹 콘텐츠를 생성하고 응답을 보내는데 사용됩니다. 
Servlet: Java 코드 안에 HTML 코드가 삽입된 형태입니다. Servlet은 주로 컨트롤러에서 요청 처리 로직을 구현하는 데 사용됩니다. 
Servlet은 Java 코드로 작성되므로 컴파일러를 통해 클래스 파일로 컴파일되어 실행됩니다
JSP: HTML 코드 안에 Java 코드가 삽입된 형태입니다.
JSP는 웹 서버에서 요청이 들어올 때 최초로 Java Servlet으로 변환(컴파일)되고, 그 후에는 Servlet처럼 동작합니다. 

-----------------------
### servlet이 컨트롤러를 담당하고, jsp가 뷰를 따로 담당하는 이유가 있나요?
Servlet(Controller): 클라이언트로부터 요청을 받아 로직을 처리하고, 적절한 View를 선택하여 결과를 보여주는 역할을 합니다.
JSP(View): Servlet에서 전달받은 데이터를 가지고 사용자에게 보여질 UI를 생성합니다.
이렇게 구성함으로써 코드의 재사용성과 유지보수성이 향상되며, 개발자는 로직 처리와 UI 디자인에 집중할 수 있습니다. 이는 더 높은 응집력을 가지며, 각 컴포넌트간의 결합력은 최소화하는 결과를 가져옵니다.

-----------------------
### jsp를 기본 제공하는 객체는 무엇이 있나요? 
request: HttpServletRequest 객체로, 클라이언트의 요청 정보를 담고 있습니다. HTTP 메서드, 요청 헤더, 쿠키, 요청 파라미터 등을 얻어올 수 있습니다.

response: HttpServletResponse 객체로, 서버의 응답을 나타냅니다. 응답 상태 코드, 응답 헤더, 쿠키를 설정하는 등의 작업을 수행할 수 있습니다.

pageContext: PageContext 객체로, 현재 페이지의 컨텍스트 정보를 담고 있습니다. 페이지의 스코프 속성을 설정하거나, 다른 범위의 속성을 얻어오는 등의 작업을 수행할 수 있습니다.

session: HttpSession 객체로, 현재 사용자 세션을 나타냅니다. 사용자 세션에 속성을 설정하거나, 세션을 무효화하는 등의 작업을 수행할 수 있습니다.

-----------------------
### 4개의 jsp scope에는 무엇이 있나요?
page : 이 범위는 JSP 페이지가 처리되는 동안에만 객체와 변수가 존재합니다. 페이지가 처리되는 동안 생성된 객체들은 페이지가 처리를 완료하면 제거됩니다.

request : 요청 범위는 하나의 클라이언트 요청이 처리되는 동안에만 객체와 변수가 유지됩니다. 클라이언트가 요청을 보내고 서버가 응답을 완료하면, 이 범위의 객체들은 제거됩니다.

session : 세션 범위는 하나의 사용자 세션이 유지되는 동안에만 객체와 변수가 존재합니다. 사용자가 웹사이트를 떠나거나 세션이 시간초과로 종료되면, 이 범위의 객체들은 제거됩니다.

application : 애플리케이션 범위는 전체 웹 애플리케이션에 대해 객체와 변수가 유지됩니다. 애플리케이션이 시작될 때 객체가 생성되고, 애플리케이션이 종료될 때 객체가 제거됩니다. 이 범위의 객체들은 애플리케이션의 모든 페이지와 사용자 세션, 요청 등에서 접근 가능합니다.

-----------------------
### 세션과 쿠키의 차이는 무엇인가요?
쿠키는 클라이언트 측에서 저장되는 작은 텍스트 파일입니다. 쿠키는 웹 사이트를 방문할 때 생성되어 사용자의 브라우저에 저장되며, 웹 사이트가 사용자를 식별하거나 이전의 활동을 기억하는데 사용될 수 있습니다.
세션은 서버 측에서 관리되는 상태 정보입니다. 사용자가 웹 사이트에 로그인하거나 정보를 입력하는 등의 상호작용을 할 때, 해당 정보는 서버에 있는 세션에 저장됩니다. 각 세션은 고유한 세션 ID를 가지며, 이는 클라이언트에게 전송되어 추후에 클라이언트가 서버에 요청을 보낼 때 해당 세션을 식별하는 데 사용됩니다.

-----------------------
### 스프링 MVC와 struts의 차이는 무엇인가요?
Spring MVC는 Spring Framework의 일부로서, 다른 Spring 모듈들과의 통합이 잘 되어 있습니다. 이는 개발자에게 데이터 액세스, 트랜잭션 관리, 보안 등의 여러 영역에서 유연성을 제공합니다. 반면에 Struts는 이런 통합 기능을 제공하지 않습니다. Spring MVC는 POJO(Plain Old Java Object) 기반의 개발 모델을 따르며, 이는 객체 지향 프로그래밍을 지원하고 코드의 테스트와 재사용을 용이하게 합니다. Struts는 Action 클래스를 상속받는 방식을 사용하는데, 이는 POJO 접근법보다는 제한적입니다.

-----------------------
### SQL Injection을 피할 수 있는 방법을 설명해주세요.
Java의 PreparedStatement를 사용하여 쿼리에 값을 직접 삽입하는 대신, 파라미터를 사용해 데이터베이스에 값을 보냅니다. 또, 입력값 검증하거나 최소 권한 원칙을 따르는 데이터베이스 사용자만 사용할 수 있게 합니다.

-----------------------
### XSS 공격이 무엇이고, 어떻게 피할 수 있는지 설명해주세요.
XSS(Cross-Site Scripting) 공격은 웹 애플리케이션에서 사용자로부터 입력받은 데이터를 적절히 검증하거나 에스케이프 처리하지 않아서, 악의적인 스크립트 코드가 웹 페이지에 삽입되어 실행되는 보안 취약점입니다.

-----------------------
### CSRF 공격이 무엇이고, 어떻게 피할 수 있는지 설명해주세요.
CSRF(Cross-Site Request Forgery) 공격은 사용자가 로그인한 상태에서 공격자가 준비한 피해 사이트를 방문하면, 그 사이트가 사용자의 명의로 공격 대상 사이트에 악의적인 요청을 보내는 공격입니다.

-----------------------
## 7. 예외 클래스
-----------------------
### throw와 throws의 차이는 무엇인가요?
throw는 실제로 프로그램에서 예외를 발생시키는 데 사용되는 키워드입니다. throws는 메소드 선언 부분에 사용되며, 해당 메소드에서 특정 타입의 예외가 발생할 수 있음을 호출자에게 알립니다.

-----------------------
### final, finally, finalize의 차이는 무엇인가요?
final : 한 번 초기화되면 그 값을 변경할 수 없습니다. 이는 상수를 선언할 때 사용됩니다.
finally : 이 키워드는 try-catch 블록에서 사용되며, 이 블록에 포함된 코드는 예외 발생 여부에 관계 없이 항상 실행됩니다. 
finalize : Object 클래스의 메서드로, 객체가 가비지 컬렉션에 의해 수거될 때 JVM에 의해 호출됩니다. 그러나 자바 9부터 이 메서드는 deprecated 되었습니다.

-----------------------
### try-catch-finally에서 생략할 수 있는 부분이 무엇인가요?
try는 절대 생략할 수 없습니다. catch와 finally 블록은 선택적입니다. 즉, 둘 중 하나는 생략할 수 있지만 둘 다 생략할 수는 없습니다.

-----------------------
### catch가 반환되면 finally가 실행되나요?
네, catch 블록에서 반환(return)문이 실행되더라도, 그 반환문은 finally 블록이 실행된 후에 실제로 반환됩니다.

-----------------------
### exception 클래스의 예시를 말해주세요.
Error : 이 클래스는 시스템 레벨의 심각한 문제, 예를 들어 OutOfMemoryError, StackOverflowError, AssertionError 등을 표현합니다.
Exception : 이 클래스는 개발자가 처리할 수 있는 수준의 예외를 나타냅니다. 이 클래스는 다시 Checked Exception과 Unchecked Exception으로 나뉩니다.
Checked Exception : 이들은 컴파일러가 체크하므로, 개발자가 반드시 이들을 처리해야 합니다.
Unchecked Exception : 이들은 주로 프로그래밍 오류로 인해 발생하며, 컴파일러가 체크하지 않습니다. 

-----------------------
## 8. Internet
-----------------------
### 301과 302 상태 코드의 의미와 차이는 무엇인가요?
이 두 상태 코드의 주된 차이는 '영구성'입니다. 웹 페이지의 URL이 영구적으로 변경된 경우 301을 사용하고, 일시적으로 변경된 경우 302를 사용해야 합니다.

-----------------------
### forward와 redirect의 차이는 무엇인가요?
forward는 주로 서버 내에서 리소스를 이동할 때 사용되며, 사용자에게 URL이 변경되지 않았음을 보여주는 경우에 적합합니다. 
redirect는 사용자가 새로운 페이지로 완전히 리다이렉트되어야 하는 경우나 다른 도메인으로 리다이렉트해야 하는 경우에 사용됩니다.

-----------------------
### tcp와 udp의 차이점을 말해주세요.
TCP는 연결형 프로토콜로, 데이터를 전송하기 전에 핸드셰이크 과정을 통해 연결을 설정합니다. 반면에 UDP는 연결형이 아닌 프로토콜로, 데이터를 보내기 전에 별도의 연결 설정 과정 없이 바로 데이터를 보냅니다.
TCP는 신뢰성 있는 데이터 전송을 보장합니다. UDP는 이러한 신뢰성을 제공하지 않으며, 패킷이 손실되거나 순서대로 도착하지 않아도 알림이나 재전송을 요청하지 않습니다.
UDP는 핸드셰이크 과정이 없고 패킷 재전송 요청이 없기 때문에 TCP보다 빠른 전송 속도를 제공합니다.
TCP는 1대1 통신만 가능하지만, UDP는 1대1, 1대다, 다대다 통신이 가능합니다.

-----------------------
### 왜 tcp는 3 handshakes를 필요로 하나요? 왜 2개가 아니죠?
3단계의 과정을 통해, 양측 모두 자신의 패킷을 수신할 준비가 되었으며, 서로가 데이터를 전송할 준비가 되었음을 확인합니다. 이는 TCP의 양방향성을 보장하고, 데이터의 순차적인 전송과 재전송을 가능하게 합니다. 그래서 3단계가 필요한 것이고, 2단계로는 이러한 확실한 확인이 이루어지지 않습니다.

-----------------------
### tcp packet은 어떻게 생성되나요?
TCP 패킷은 TCP 세그먼트라고도 불리며, IP 패킷의 데이터 부분에 캡슐화되어 네트워크를 통해 전송됩니다. 각 TCP 패킷은 헤더와 데이터로 구성됩니다. TCP 패킷이 생성되면 IP 패킷 내에 캡슐화되어 전송됩니다. TCP의 헤더 정보는 패킷의 전송과 수신을 제어하며, 데이터 부분은 사용자의 실제 데이터를 담고 있습니다.

-----------------------
### OSI 7계층에 대해서 설명해주세요.
물리 계층 (Physical Layer): 이 계층은 데이터의 실제 전송을 담당합니다. 물리적인 매체(예: 케이블, 라디오파, 광섬유 등)를 통해 비트를 전송합니다.
데이터 링크 계층 (Data Link Layer): 이 계층은 물리 계층에서 전송된 데이터의 에러를 감지하고 교정합니다. 또한 프레임의 전송 순서를 관리하고 네트워크 상의 충돌을 관리합니다.
네트워크 계층 (Network Layer): 이 계층은 데이터 패킷의 경로를 결정합니다. 이 계층은 라우터와 같은 장치에서 작동하며 IP 주소를 관리하고, 라우팅 알고리즘을 사용해 최적의 경로를 결정합니다.
전송 계층 (Transport Layer): 이 계층은 데이터의 전송을 관리합니다. TCP와 UDP와 같은 프로토콜이 이 계층에서 작동하며, 데이터를 세그먼트로 분할하고 이를 패킷으로 재조립하는 역할을 합니다.
세션 계층 (Session Layer): 이 계층은 네트워크 간의 세션을 설정, 관리, 종료합니다. 이 계층은 통신 세션의 시작과 끝을 담당합니다.
표현 계층 (Presentation Layer): 이 계층은 데이터의 형식을 관리합니다. 이 계층에서 데이터는 사용자 시스템에서 이해할 수 있는 형식으로 변환되거나, 네트워크 형식으로 변환될 수 있습니다.
응용 계층 (Application Layer): 이 계층은 사용자와 가장 가까운 계층입니다. 웹 브라우저, 이메일 클라이언트와 같은 응용 프로그램이 이 계층에서 작동합니다.

-----------------------
### get과 post요청의 차이를 말해주세요.
GET은 서버에서 정보를 조회하기 위해 사용됩니다. GET 요청은 URL에 파라미터를 포함시킵니다. 
POST는 서버에 정보를 제출하기 위해 사용됩니다. POST 요청은 데이터를 HTTP 메시지 본문에 담아 전송합니다.

-----------------------
### 어떻게 도메인 간의 요청이 작동하나요?
DNS 조회 : 웹 브라우저는 도메인 이름에 대응하는 IP 주소를 찾기 위해 DNS 조회를 수행합니다. 이 과정에서 DNS 서버에게 도메인 이름에 해당하는 IP 주소를 요청하게 됩니다.
IP 주소 수신 : DNS 서버는 도메인 이름에 해당하는 IP 주소를 웹 브라우저에 반환합니다.
HTTP 요청 전송 : 웹 브라우저는 이 IP 주소를 사용하여 해당 서버에 HTTP 요청을 전송합니다. 이 요청은 GET, POST 등의 HTTP 메서드를 포함할 수 있으며, 특정 웹 페이지나 리소스를 요청하는 정보를 포함합니다.
HTTP 응답 수신 : 웹 서버는 HTTP 요청을 처리하고, 요청한 데이터와 함께 HTTP 응답을 웹 브라우저에 전송합니다. 이 응답은 일반적으로 웹 페이지의 HTML 코드를 포함합니다.
웹 페이지 렌더링 : 웹 브라우저는 받은 HTML 코드를 분석하고 렌더링하여 사용자에게 웹 페이지를 표시합니다.

-----------------------
### JSONP가 무엇인가요?
JSONP(JSON with Padding)는 Single-Origin Policy나 CORS(Cross-Origin Resource Sharing)에 의해 제한되지 않는 script 태그를 이용해 도메인 간 데이터를 전송하는 방식입니다.

-----------------------
### 디자인 패턴에 대해 말해주세요.
디자인 패턴은 특정 문제나 상황에서 반복적으로 발생하는 설계 문제를 해결하는 데에 일반적으로 사용되는 체계화된 최선의 방법을 가리킵니다. 
생성 패턴은 객체가 생성되는 방식을 중심으로 설계되며, 객체의 생성 과정과 클래스의 결합도를 최소화합니다. 
주요 생성 패턴에는 Singleton, Factory Method, Abstract Factory, Builder, Prototype 등이 있습니다.
구조 패턴은 클래스나 객체를 더 큰 구조로 구성하는 패턴입니다. 이들은 클래스의 구조를 구성하여 클래스나 객체의 기능을 확장하거나 독립적으로 작동하게 만듭니다. 
주요 구조 패턴에는 Adapter, Bridge, Composite, Decorator, Facade, Flyweight, Proxy 등이 있습니다.
행동 패턴은 객체나 클래스 사이의 알고리즘이나 책임 분배에 대한 패턴입니다. 이들은 객체 간의 통신과 책임 분배를 중점으로 다룹니다. 
주요 행동 패턴에는 Command, Interpreter, Iterator, Mediator, Memento, Observer, State, Strategy, Template Method, Visitor 등이 있습니다.

-----------------------
### 심플 팩토리와 추상 팩토리의 차이가 무엇인가요?
Simple Factory 패턴은 클래스의 인스턴스를 생성하는 "팩토리" 메서드를 제공합니다. Abstract Factory 패턴은 연관된 또는 의존적인 객체들을 생성하는 인터페이스를 제공합니다. 

-----------------------
## 9. Spring
-----------------------
### 스프링 사용의 장점은 무엇인가요?
Inversion of Control (IoC) / Dependency Injection (DI): 스프링은 객체의 생명주기와 의존성을 관리해주는 IoC 컨테이너를 제공합니다. 이를 통해 개발자는 각 객체 간의 의존성 관리에 신경 쓰지 않아도 되며, 코드의 결합도를 낮출 수 있습니다.

Aspect-Oriented Programming (AOP): 스프링은 관점 지향 프로그래밍을 지원합니다. 이를 통해 반복적인 코드를 줄이고, 프로그램의 모듈성을 높일 수 있습니다.

포괄적인 데이터 접근 지원: 스프링은 JDBC, JPA, Hibernate 등 다양한 데이터 접근 기술을 추상화한 spring-data 모듈을 제공합니다. 이를 통해 데이터 액세스 계층의 코드를 단순화하고, 일관성을 유지할 수 있습니다.

트랜잭션 관리: 스프링은 선언적 트랜잭션 관리를 지원합니다. 이를 통해 개발자는 복잡한 트랜잭션 API를 직접 다루지 않아도 됩니다.

MVC 웹 프레임워크: 스프링은 모델-뷰-컨트롤러 패턴을 기반으로 한 강력한 웹 프레임워크인 Spring MVC를 제공합니다.

테스트 지원: 스프링은 JUnit과 함께 통합 테스트를 위한 클래스를 제공합니다. 이를 통해 스프링 컨텍스트를 로드하고 DI를 수행하며, 테스트 데이터를 DB에 적용하는 등의 작업을 쉽게 수행할 수 있습니다.

다양한 통합 지원: 스프링은 이메일, JMS, 웹 서비스 등 다양한 기술에 대한 통합을 지원합니다.

-----------------------
### AOP란 무엇인가요?
AOP (Aspect-Oriented Programming, 관점 지향 프로그래밍)는 크로스 커팅 (cross-cutting) 관심사를 분리하여 코드의 모듈성을 높이는 것을 목표로 합니다.
AOP는 일반적으로 로깅, 트랜잭션 관리, 보안 등과 같은 기능을 프로그램 코드의 여러 부분에서 공통으로 사용하는 경우에 유용합니다. 이런 종류의 코드는 애플리케이션의 주요 비즈니스 로직과는 직접적인 관련이 없지만, 그럼에도 불구하고 필요한 코드입니다. 이러한 기능을 별도의 "관심사(Aspect)"로 분리하면, 애플리케이션의 나머지 부분에서는 이들을 신경 쓸 필요 없이 주요 비즈니스 로직에만 집중할 수 있습니다. 이는 코드의 재사용성과 유지 관리성을 향상시키는 데 기여합니다.

-----------------------
### IOC란 무엇인가요?
IOC(Inversion of Control, 제어의 역전)는 프로그램의 흐름 제어를 개발자가 아닌 프레임워크 또는 컨테이너에 위임하는 개념입니다.
IOC의 주요 목표는 코드의 결합도를 줄이고 모듈 간의 독립성을 높여 유지보수와 테스트를 용이하게 하는 것입니다. 
스프링 프레임워크의 주요 원칙 중 하나인 Dependency Injection (의존성 주입)은 IOC의 특정 형태입니다. Dependency Injection은 객체가 필요로 하는 다른 객체(의존성)를 외부에서 주입받아 사용하는 기법으로, 이를 통해 객체 간의 결합도를 낮추고 유연한 코드를 작성할 수 있습니다.

-----------------------
### 스프링의 메인 모듈은 무엇인가요?
Spring Core: 스프링의 핵심 기능인 제어의 역전(Inversion of Control, IoC)과 의존성 주입(Dependency Injection, DI)을 제공합니다.

Spring AOP (Aspect Oriented Programming): 공통 관심사를 분리하고 코드 모듈화를 돕는 AOP를 지원합니다.

Spring DAO: 데이터베이스 연산을 처리하는 DAO(Data Access Object)를 지원합니다. JDBC와 같은 예외처리와 리소스 관리를 단순화해줍니다.

Spring ORM: Hibernate, JPA 등 주요 ORM(Object-Relational Mapping) 프레임워크와의 통합을 지원합니다.

Spring Web MVC: 웹 애플리케이션을 위한 MVC(Model-View-Controller) 프레임워크를 제공합니다.

Spring WebFlux: 비동기 처리와 리액티브 프로그래밍을 지원하는 웹 프레임워크입니다.

Spring Security: 애플리케이션의 보안 관련 기능을 제공하는 프레임워크로, 인증, 권한 부여, 공격 방어 등의 기능을 제공합니다.

Spring Boot: 스프링 기반 애플리케이션을 빠르게 개발할 수 있도록 돕는 도구로, 기본 설정, 서버 설정 등을 자동화해줍니다.


-----------------------
### 가장 많이 사용되는 의존성 주입 방법은 무엇인가요?
Constructor Injection: 생성자를 통해 의존성을 주입하는 방법입니다. 이 방법은 의존성이 변경되지 않고, 객체 생성 시점에 모든 의존성이 주입되기 때문에 객체의 불변성을 보장합니다. 따라서, 객체의 안전성이 중요한 경우에 많이 사용됩니다.
Field Injection: 직접 필드에 @Autowired 어노테이션을 붙여서 의존성을 주입하는 방법입니다. 이 방식은 코드량이 가장 적지만, 테스트와 재사용성 측면에서는 단점이 있습니다.
Setter Injection: Setter 메소드를 통해 의존성을 주입하는 방법입니다. 이 방식은 간단하며, 객체가 완전히 생성된 후에 필요한 의존성을 설정할 수 있다는 장점이 있습니다.
이 중 Constructor Injection이 권장된다.
