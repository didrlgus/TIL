## Q. == 과 equals()의 차이는 뭘까요?
* `동일성과 동등성`에 대한 차이입니다. 
* == 은 비교대상이 primitive type이면 값 비교, reference type이면 참조값을 비교하여 boolean 값을 리턴합니다.
* 즉, == 은 동일성 비교입니다.
* equals()는 Object 클래스에 정의된 메서드이며 기본적으로는 동일성 비교 입니다. 
* 단, equals()는 하위 클래스에서 재정의가 가능하며 이를 통해 값 비교인 동등성 비교가 가능합니다.
* 하지만, equals()를 재정의 할때는 주의점이 있는데요.
* 먼저 equals()는 하위클래스에서 객체들간에 메모리 주소를 기반으로 물리적으로 같은지에 대한 동일성 비교가 아닌, 객체 내 각 속성들의 값이 같은지에 대한 동등성 비교를 해야할 때 재정의 해야합니다.
* 이때, equals() 재정의 지켜야 할 다섯가지 규약이 있는데요.
* 반사성 (reflexivity), 대칭성(symmetry), 추이성(transitivity), 일관성(consistency), null-아님 이 다섯가지 규약입니다.
* 또한, equals()를 재정의 한다면, `hashcode()` 또한 재정의 해야 합니다.
* 그렇지 않으면, hashcode() 값을 사용하는 Collection인 `HashSet, HashMap, HashTable`을 사용할 때 문제가 발생할 수 있습니다.
* HashSet에서는 객체간의 중복여부를 파악할 때 hashcode()를 사용하고, HashMap과 HashTable에서는 key의 중복여부를 파악할 때 hashcode를 사용하기 때문입니다.
* 즉, hashcode()로 인한 문제를 일으키지 않기 위해서는 `재정의 한 equals()의 반환 값이 true 라면, 두 객체의 hashcode()도 마찬가지로 동일한 값을 반환시킬 수 있게 재정의` 해야 합니다.
* `이와 반대로, equals()의 반환 값이 false 라고 하더라도, 두 객체의 hashcode() 값이 꼭 달라야 할 필요는 없습니다.`  
* 다만, equals() 값이 false인 객체들에 대해서는 서로 다른 hashcode() 값을 반환해야 해시테이블의 충돌을 최소화 시킬 수 있고 성능을 높일 수 있습니다.