## Q. String literal 과 new String(“”) 의 차이를 설명하세요. 특히 JVM 관점에서의 차이를 말씀해 주시기 바랍니다
* "" 방식으로 생성된 문자열 객체는 Heap 내의 별도 공간인 `String Constant Pool`에 생성됩니다.
* String Constant Pool 내에 생성되는 문자열은 `중복되지 않습니다.`
* 그 이유는 String 객체를 literal 객체로 만들면 내부적으로 String class에 정의된 `intern()` 메서드가 호출되기 때문입니다.
* intern() 메서드에서는 생성하고자 하는 문자열이 String Constant Pool에 존재하는지 검색하고 있다면 기존에 문자열이 저장된 참조값을 반환하고, 
  없다면 String constant pool에 새로운 String 객체를 할당하고 새로운 참조값을 반환하는 방식으로 동작합니다.
* 또한, constant pool에 생성되는 String 객체는 `immutable`한 특징을 갖습니다.
* 그리고, String constant pool 역시 GC의 대상이 될 수 있습니다.  
* 반면에, new 연산자 방식으로 생성된 String 객체는 일반 클래스로 부터 만들어지는 객체와 마찬가지로 Heap에 생성되며, 중복해서 할당이 가능하고, mutable한 특징을 갖습니다.
* 결과적으로, literal 방식으로 생성된 String 객체의 중복방지와 immutable한 특징은 메모리 공간을 효율적으로 사용할 수 있다는 장점을 가집니다.
* 다만, `문자열 간의 연산 작업`에서는 연산의 결과 값을 Constant Pool의 새로운 메모리 공간에 추가시켜야 하므로 `비효율적`입니다.
* 이처럼 문자열 연산작업이 많이 필요할 경우에는 String 대신 `StringBuffer나 StringBuilder`를 사용합니다.
* StringBuffer와 StringBuilder는 String 보다 문자열 연산작업에 있어서 메모리 공간을 더 효율적으로 사용할 수 있습니다.
* StringBuffer와 StringBuilder의 차이는 StringBuffer가 multi thread 환경에서 thread-safe한 특징을 갖는다는 것입니다.

