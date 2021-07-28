## Q. ConcurrentModificationException 을 설명해주세요.
* ConcurrentModificationException 예외는 Multi threads 환경 또는 객체의 변경이 허용되지 않는 환경에서 concurrent modification이 일어날 때 이 예외가 발생할 수 있습니다.
* 예를들면, 한 스레드가 Collection을 Iterating 하고 있을 때 다른 스레드에서 Collection을 modify 하는 경우, ConcurrentModificationException이 발생할 수 있습니다.
* 그리고 싱글 스레드 환경에서도 Collection을 fail-fast iterator하고 있을 때 Collection을 modify 하는 경우에도 ConcurrentModificationException이 발생할 수 있습니다. 
* 여기서 말하는 modify는 Collection의 사이즈를 변경시키는 행동을 말합니다. (e.g add() or remove())
* 이를 해결하기 위한 방법으로는 Iterator를 이용한 방법과, Stream API를 이용하는 방법이 있습니다.