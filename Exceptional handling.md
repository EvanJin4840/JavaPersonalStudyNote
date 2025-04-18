| 항목                  | Checked Exception                             | Unchecked Exception                             |
|-----------------------|-----------------------------------------------|-------------------------------------------------|
| 예외 처리 강제 여부      | ✅ 컴파일 시 예외 처리 **필수**                  | ❌ 예외 처리 **선택적** (컴파일러가 강제하지 않음)     |
| 발생 시점              | 주로 외부 자원 (파일, DB, 네트워크 등) 관련 예외     | 주로 코드 논리 오류 (나누기 0, 널 접근 등)             |
| 상속 계열              | `Exception` (단, `RuntimeException` 제외)       | `RuntimeException` 및 그 하위 클래스                   |
| 예시                  | `IOException`, `SQLException`, `FileNotFoundException` | `NullPointerException`, `ArithmeticException`, `IndexOutOfBoundsException` |
| 처리 방법              | `try-catch` 또는 `throws` 사용 **필수**            | 필요 시 `try-catch` (처리 안 해도 컴파일 가능)         |

| 키워드      | 설명                                        | 예시 코드                                                   |
|-------------|---------------------------------------------|-------------------------------------------------------------|
| `throw`     | 예외를 **직접 발생**시킴                         | `throw new IllegalArgumentException("잘못된 입력");`         |
| `throws`    | 예외를 **메서드 바깥으로 던질 수 있음**을 선언       | `public void readFile() throws IOException { ... }`         |
| `try-catch` | 예외 발생 코드 감싸고, 발생 시 처리                  | `try { ... } catch (Exception e) { ... }`                   |
