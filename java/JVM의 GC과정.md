## Q. GC의 동작방식에 대해 설명해주세요.
* GC의 세부 동작방식을 말씀드리기에 앞서 heap의 구조를 알고 있어야 합니다. 
* heap은 크게 young gen과 old gen으로 나뉩니다.
* young gen은 새로 생성된 객체들이 할당되는 영역이고 old gen은 young gen에서 오래 살아남은 객체들이 존재하는 영역입니다.
* 그리고 young gen은 다시 eden 영역과 두개의 survivor 영역으로 나뉩니다. 앞으로 이 두개의 survivor 영역을 각각 survivor-1,survivor-2라고 가정하겠습니다.
* heap 영역을 나누는 이유는 heap 전체를 탐색하여 메모리를 해제하는 `full gc` 로 인한 성능상의 이슈를 최소화 시키기 위함입니다.
* 또한, survivor 영역을 두개로 나누는 이유는 `메모리 단편화` 문제를 해결하기 위함입니다.
* 그럼, 이제부터 GC의 동작과정에 대해서 말씀드리면 먼저 새로 생성된 객체들은 eden 영역에 추가됩니다. 
* 그리고 eden 영역이 가득차면 young gen을 대상으로 `mark and sweep` 작업이 수행되는데 이를 `minor gc`라고 부릅니다.
* 이떄, gc를 수행하는 쓰레드를 제외한 모든 스레드를 멈추는 현상이 발생하는데, 이를 `stop the world`라고 합니다.
* `minor gc` 작업을 통해서 reachable 한 객체는 살아남고 unreachable한 객체는 제거됩니다. 그리고 'minor gc' 작업을 통해 살아남은 reachable한 객체는 survivor1 또는 survivor2 영역중 한곳으로 이동합니다.
* 이때, 객체가 survivor1과 survivor2에 공존하지 않고 어느 한 영역에만 존재합니다.
* 그리고 survivor로 이동된 살아남은 객체는 age가 하나씩 추가됩니다. 
* 위의 과정이 반복되면서 하나의 survivor 영역이 가득 차게 되면 `minor gc`가 수행되고 그 중에서 살아남은 객체를 다른 Survivor 영역으로 이동시킵니다. 
* 그리고 이전 Survivor 영역은 아무 객체도 없는 상태로 비워둡니다.
* 위의 과정을 반복하다 survivor에 있는 객체의 age가 특정 임계점에 다다르면 해당 객체는 old gen으로 이동되는데 이 과정을 `promotion`이라고 합니다.
* 위의 모든 과정을 반복하면서 old gen이 가득차게 되면 old 영역을 대상으로 gc 작업을 수행하는데 이를 `major gc` 라고 합니다.
