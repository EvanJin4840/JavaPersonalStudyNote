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
