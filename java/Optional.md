## Q. Optional 이란 무엇을 하는 클래스일까요? 이게 왜 나왔을까요?
* Optional은 generic class로 'T 타입의 객체'를 감싸는 wrapper class 입니다.
* 그래서 Optional 타입의 객체에는 모든 타입의 참조변수를 담을 수 있습니다.
* 메서드의 return 값을 그냥 반환하는 것이 아니라 Optional 객체에 담아서 반환하면, 반환된 결과가 null인지 매번 if문으로
  체크하는게 아니라 Optional에서 제공해주는 기본 메서드들을 이용해 쉽게 null check를 할 수 있습니다.
* 즉, Optional은 NullPointerException으로부터 자유로워지기 위해 나왔고, null 처리를 개발자가 직접하지 않고 Optional 클래스에 위임할 수 있습니다.  