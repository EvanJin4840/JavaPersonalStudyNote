### Throw

- throw를 쓸 때에는 무조건 new로 예외 객체를 생성해서 던져야 함.
이유? throw는 ``예외 객체를 던지는 것``이기 때문에, new로 **예외 클래스의 인스턴스(객체)**를 만들어야 하기 때문임.

- 질문 2: 만약 throw는 하나인데, catch블록이 여러 개 있는 경우엔, "어떤 catch로 들어가는지"는 어떻게 결정되는가? -> 예외는 던져진 객체의 타입(class)와 catch문에 지정된 예외 타입과의 일치 여부를 기반으로 가장 먼저 일치하는 catch블록으로 들어감.
여기서 객체의 타입(class)는 예시 코드에서 ArthmeticException을 의미함. 
예시 코드:

``try {
    throw new ArithmeticException("0으로 나눔");
} catch (ArithmeticException e) {
    System.out.println("수학 예외 처리!");
}``

* 일치 판별 예시

| throw된 객체             | catch문 타입              | 일치?           |
| --------------------- | ---------------------- | ------------- |
| `ArithmeticException` | `ArithmeticException`  | ✅ 정확히 일치      |
| `ArithmeticException` | `RuntimeException`     | ✅ 부모 타입, 상속받음 |
| `ArithmeticException` | `Exception`            | ✅ 조상 타입       |
| `ArithmeticException` | `NullPointerException` | ❌ 전혀 다른 예외    |

* 그렇다면 왜 굳이 예외 클래스를 만들고, super(message)등으로 넘기는 것인가? 비효율적인 것이 아닌가? -> super(message)를 쓰는 이유는 단순 출력 때문이 아니라,
**"예외 객체 안에 그 메시지를 구조적으로 저장해서, 프로그램 흐름에 따라 재사용하고 전달하기 위해서"**임. 예외 처리의 목적은 출력이 아니라 프로그램 흐름 제어와 책임 분리이다.

* throw만 쓰면 컴파일 에러! 반드시 try-catch 또는 throws가 필요합니다.

- 질문: 예외가 여러 종류일 수 있는데, try문만 쓰면 어떤 예외인지를 자바가 어떻게 알 수 있나요?
예를 들어, 입력이 너무 길거나, 문자열이거나, 이상한 문자인 경우 각각 다르게 처리하고 싶을 때
→ try만 써도 되는가? 아니면 if가 꼭 필요한가?
-> 답변: try-catch는 "실제로 예외가 발생하는 상황만 처리"할 수 있고,
조건을 미리 걸러내야 하는 경우(예외가 발생하지 않는 잘못된 입력)는 if가 필요합니다.
즉,
문법적으로 잘못된 입력 → 자바가 예외 던짐 → catch로 처리 가능
형식은 맞지만, 논리적으로 잘못된 입력 → 예외 안 남 → if로 검사해야 함
