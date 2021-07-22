## Q. 자바의 어노테이션에 대해 설명해주세요.
* annotation이란 java의 소스코드를 설명하는 메타데이터 입니다.
* annotation을 이용하면, 컴파일러에게 소스코드에 대한 문법 에러를 체크하도록 정보를 제공할 수 있습니다.
* 그리고 런타임 시 특정 기능을 실행하도록 정보를 제공할 수 있습니다.
* 또한, 컴파일 시 코드를 자동으로 생성할 수 있도록 정보를 제공할 수 있습니다.
* annotation은 크게 Built-in, Meta, Custom annotation으로 나뉩니다.
* Built-in annotation은 이미 Java에 내장되어 있는 annotation을 말합니다. 
* 주로 컴파일러에게 해당 소스코드에 대한 문법 에러를 체크하도록 정보를 제공하며, 대표적으로 @Override가 있습니다.
* Meta-annotation은 annotation에 사용되는 annotation으로 해당 annotation의 동작 대상 및 유지 기간 등을 결정합니다.
  대표적으로 @Target, @Retention이 있습니다.
* Custom annotation은 개발자가 직접 선언한 annotation을 말합니다.
* Java의 reflection API를 통해 annotation이 붙은 멤버를 식별할 수 있으며, 이를 이용한 기능중 하나가 스프링의 의존성 주입입니다.
* 또한, annotation processor를 이용하면, 소스코드 레벨에서 소스코드에 붙어있는 annotation 정보를 읽어서 컴파일러가 컴파일 하는 중에 새로운
  소스코드를 생성하거나 기존의 코드를 변경할 수 있습니다. 대표적인 예로 Lombok이 있습니다.
