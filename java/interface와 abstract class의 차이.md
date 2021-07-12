## Q. interface와 abstract class 차이는 무엇일까요?
* 자바 8에서는 default 키워드가 추가되어 interface에서도 메서드의 내용을 구현할 수 있게 되면서, interface와 abstract class 간의 차이가 없어진 것으로 보일 수 있습니다.
* 하지만, 사실 class의 근본적인 정의의 관점에서 볼 때, interface와 abstract class 간에는 중요한 차이점이 존재합니다.
* 먼저, interface는 `상태(속성)를 갖지 않습니다.`
* 또한, interface는 모든 멤버의 접근 제어자가 public 입니다.
* interface의 모든 멤버의 접근 제어자가 public인 이유는 interface를 구현한 구현체에서 정의된 메서드는 클라이언트에게 public으로 노출돼야 하기 때문입니다.
* 결론적으로 인터페이스는 클라이언트가 해당 메서드를 어떻게 사용할지에 대한 `계약`을 제공합니다.
* 반면에, abstract class는 기본적으로 class로써 `상태(속성)와 행위`를 갖습니다.
* 그리고, abstract class는 interface와 다르게 해당 멤버들의 접근 제어자가 public일 필요는 없습니다.  
* 결론적으로 abstract class는 해당 class를 확장할 class에게 `기본적인 context를 제공`합니다.
* 그렇다면 interface는 언제 사용하고, abstract class는 언제 사용하는 것이 좋을까요?
* 이는, 둘의 `사용목적`의 관점에서 바라볼 필요가 있습니다.
* 인터페이스는 해당 인터페이스를 구현한 구현체들이 같은 행위를 한다는 것을 클라이언트에게 명시하기 위함이 목적입니다.
* 그에 반해, abstract class는 상위 클래스에서 공통된 기능은 그대로 물려받거나 혹은 별도로 구현하고, 새로운 속성과 행위를 확장하기 위함이 목적입니다.
* 하지만, 꼭 필요한 경우를 제외하고는 상속을 피하는 것이 좋은 설계라고 생각합니다.
* 상속은 특성상 서브 클래스가 슈퍼클래스의 상태와 행위를 공유하기 때문에 서브 클래스는 슈퍼클래스에 의존하는 관계가 되고, 이로인해, 둘간의 결합도가 높아져 코드의 유연성을 떨어뜨릴 수 있다는 단점이 있기 때문입니다.
* 그에반해, 인터페이스는 `어떠한 상태도 가지지 않으며`, 행위에 대한 조건(parameter)과 결과(return) 타입만 강제할뿐 내용에 대한 구현은 하위 클래스에게 맡기기 때문에, 의존관계가 생기지 않고, 결합도가 느슨해 코드의 유연성을 높일 수 있다는 장점이 있습니다.
* 결론적으로, 정말 꼭 abstract class가 필요한 IS-A 관계를 제외한 나머지 상황에서는 interface를 사용하는 것이 좋은 설계라고 생각합니다.

## Q. 그렇다면 추상화가 무엇인가요?
* 추상화
  * 클래스간의 공통점을 찾아내서 공통의 조상을 만드는 작업 (자바의 정석)
  * 공통의 속성이나 행위를 묶어 이름을 붙이는 것 (https://88240.tistory.com/228)
  * Abstraction is the concept of object-oriented programming that "shows" only essential attributes and "hides" unnecessary information. The main purpose of abstraction is hiding the unnecessary details from the user. (https://www.guru99.com/java-data-abstraction.html)