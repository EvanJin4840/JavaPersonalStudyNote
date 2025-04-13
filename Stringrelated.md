### .substring 메소드

- public String substring(int startIndex)

startIndex부터 끝까지의 문자열을 리턴합니다.
ex) str = "Hello", str.substring(2) = "llo", H=str[0], e=str[1]임
startIndex로 음수값이나, 범위를 벗어나는 값을 입력하면 ->StringIndexOutOfBoundsException이 발생

- public String substring(int startIndex, int endIndex)

stratIndex부터 endIndex까지의 문자열을 잘라서 리턴합니다.
(정확하게는 startIndex부터 lastIndex 전까지의 문자열을 잘라서 리턴함.)
* str.substring(2, str.length());를 사용하면, substring(2)와 같은 의미 -> startIndex 2부터 마지막 문자열까지를 잘라서 리턴합니다.

* 출처:https://hianna.tistory.com/534

### 자바의 문자열 처리 (입력, 한 자씩 읽기, 자르기)
https://eijun.tistory.com/16

Integer.parseInt(String s)
숫자형의 문자열을 인자 값으로 받으면 해당 값을 10진수의 int형으로 반환 해줍니다.

Integer.parseInt(String s, int radix)
숫자형의 문자열을 첫번째 인자 값으로 받고 변환할 진수값을 입력하면 해당 진수에 맞춰 int(Primitive type) 형으로 반환하여 줍니다.

출처:https://jamesdreaming.tistory.com/125

* 참고: Integer.valueOf()는 반환 타입이 Integer(Reference Type)임.

#### 2, 8, 10, 16진수가 모두 int 타입 값으로 저장되는 이유

- 컴퓨터는 모든 수를 이진수(0과 1)로 저장함. 2진수, 16진수.. 등은 "표현 방식" 즉 **"사람이 읽는 형식"**일 뿐임.

##### 번외🔢 정수(int)를 다른 진수 문자열로 출력하는 방법

| 메서드                          | 설명                | 예시 출력 (`x = 255`) |
|----------------------------------|---------------------|------------------------|
| `Integer.toBinaryString(x)`     | 2진수 문자열로 변환 | `"11111111"`          |
| `Integer.toOctalString(x)`      | 8진수 문자열로 변환 | `"377"`               |
| `Integer.toHexString(x)`        | 16진수 문자열로 변환| `"ff"`                |

### 자바에서 String타입 문자열을 비교할 때

* 자바에선 C++과 다르게 `==` 연산자로는 문자열이 같은지 확인할 수 없음, `==` 연산자는 객체의 메모리 주소(참조)를 비교하는 것임.
    - 즉 두 변수가 같은 객체를 가리키고 있는지를 확인하는 것이고, 실제 값이 같은지를 비교하는 것이 아님
* 실제 값을 비교하는 방법
    - equals()메소드를 사용한다. ex)str1.equals(str2)와 같이 사용한다.