## Q. Inner class와 Nested class가 무엇인가요?
* 자바에서는 class 안에 class를 선언할 수 있습니다.
* 이렇게, class 안에 선언된 class를 Nested class라고 부릅니다.
* Nested class는 특정 class가 한 곳에서만 사용될 경우, 논리적으로 군집화하기 위해 사용합니다.
* 이로 인해, 불필요한 외부 노출을 줄이면서 캡슐화를 할 수 있고, 가독성을 높이며 유지 보수하기 좋은 코드를 작성할 수 있습니다.
* Nested class는 선언 방식에 따라 Static nested class, Inner class로 나뉘고, 또 Inner class는 Local Inner class와 Anonymous class로 나뉩니다.
* Static nested class와 Inner class의 차이는 static으로 선언되었는지의 여부입니다.
* 먼저, Static nested class는 해당 class를 감싸고 있는 Outer class의 static으로 선언된 멤버를 제외한, 어떠한 멤버에도 접근할 수 없습니다.
* 그에 반해, Inner class는 Outer class의 모든 멤버에 접근이 가능합니다.  
* 그리고 Static nested class의 객체는 Outer class 객체와 관계없이 독립적으로 객체를 생성할 수 있습니다.
* 그에 반해, Inner class는 Outer class의 객체를 생성한 뒤 해당 객체를 이용해서 객체를 생성할 수 있습니다.
* Inner class의 경우 기본적으로 Outer class에 대한 참조를 갖고 있습니다. 
* 그렇기 때문에, Outer class는 더 이상 사용되지 않더라도, Inner class의 참조로 인해 GC의 대상이 되지 않아 Outer class의 메모리 헤제를 하지 못하는 메모리 누수의 가능성이 있습니다.
* 결론적으로, Nested class가 필요한 상황에서 Outer class에 대한 멤버를 참조하지 않는 상황이라면, 무조건 Static nested class로 선언해주는 것이 좋습니다.

## Q. Anonymous class에 대해서 설명해주세요.
* Anonymous class는 Inner class의 일종입니다.
* 다만, Anonymous class는 특이하게도 다른 Inner class와 달리 이름이 없습니다.
* class의 선언과 객체의 생성을 동시에 하기 때문에 단 한번만 사용될 수 있고, 오직 하나의 객체만을 생성할 수 있는 일회용 class입니다.
* 이름이 없기 때문에, 생성자를 가질 수 없으며 오로지 단 하나의 class를 상속 받거나 단 하나의 interface만을 구현할 수 있습니다.
