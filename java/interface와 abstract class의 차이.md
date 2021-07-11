## Q. interface와 abstract class 차이는 무엇일까요?
* 자바 8에서는 default 키워드가 추가되어 interface에서도 메서드를 정의할 수 있게 되면서, interface와 abstract class 간의 차이가 없어진 것으로 보일 수 있습니다.
* 하지만, 사실 class의 근본적인 정의의 관점에서 볼 때, abstract class와 interface 간에는 중요한 차이점이 존재합니다.
* abstract class는 기본적으로 class로써 상태(속성)와 행위를 갖습니다.
* 하지만, interface는 상태(속성)를 갖지 않습니다.
* 또한, interface는 모든 멤버의 접근 제어자가 public이지만, abstract class는 public일 필요가 없습니다.
* interface는 모든 멤버의 접근 제어자가 public인 이유는 interface를 구현한 구현체에서 정의된 메서드는 클라이언트에게 public으로 노출돼야 하기 때문입니다.
* 즉, interface는 interface를 구현하는 것에 대해서 클라이언트에 다형성을 제공하는 역할도 하지만, 결론적으로는 클라이언트가 해당 메서드를 어떻게 사용할지에 대한 계약을 제공한다.
* 반면에, abstract class는 해당 class를 확장할 class에게 기본적인 context를 제공합니다.