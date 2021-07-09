### Q. == 과 equals()의 차이는 뭘까요?
<details>
    <summary style="font-Weight : bold; font-size : 50px; color : #E43914;">답변</summary>
    <div>
        <p>
            동일성과 동등성에 대한 차이입니다.
            ==은 비교대상이 primitive type이면 값 비교, reference type 주소를 비교하여 boolean 값을 리턴합니다.
            즉, ==는 동일성 비교입니다.
            equals()는 Object 클래스에 정의된 메서드 이며 하위 클래스에서 오버라이딩을 통해 값비교가 가능합니다.
            대표적인 예로 String 클래스가 있습니다.
        </p>
    </div>
</details>