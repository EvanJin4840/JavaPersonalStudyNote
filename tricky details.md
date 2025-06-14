### 메소드 뿐 아니라 반복문(while 등) 내에서 변수를 선언하게 되면, 해당 반복문(유효 범위, scope)을 빠져나오는 순간 그 변수는 사용이 불가능하게 됨! ("소멸됨"), (C++에서도 마찬가지임)

### nextInt() 직후, nextLine()을 하게되면, nextLine()이 enter를 입력받아버려서 빈 문자열을 즉시 읽어버리게 되므로, 중간에 nextLine()을 한번 더 사용하여서 enter를 없애야 한다.

### 자바에선 메서드 안에 메서드를 선언할 수 없음.
* public static void main(String[] args)메서드 안에도 다른 메서드를 선언할 수 없음!

### 자바에선 class타입명(Person) 변수명(a);만 하면 a는 아직 아무 객체도 가리키지 않는 상태임
* 해결 방법: new Person()을 해야 진짜 객체(인스턴스)를 힙(heap)에 생성하고 a가 그걸 가리키게 됨.
- 자바에선 C++과 다르게, stack에 객체를 직접 올리지 않기에 모든 객체는 힙 메모리에 생성해 -> 즉 객체를 만들 때는 항상 new를 사용해야 함
+ 참고: 기본형(int, double, boolean)은 스택에 저장
+ 참조형(String, Scanner, 선언한 클래스명 등)은, 힙에 생성 후, 스택에 참조값 저장

### Stack 및 Heap이란?
* 스택 : 지역 변수, 기본형 저장 / 참조형의 참조값(주소) 저장 (메서드 호출 시 생기는 임시적이고 빠른 메모리 공간)
* 힙 : new로 생성된 객체들이 실제로 저장되는 동적 메모리 공간, 객체가 생성되는 곳

### 기본형과 참조형
- 기본형 : 숫자, 문자처럼 단순한 값 → 복사해도 독립적
- 참조형 : 클래스, 배열, 문자열 → 복사해도 같은 객체 참조함

| 비교 항목       | 기본형 (Primitive Type)     | 참조형 (Reference Type)            |
|------------------|-------------------------------|-------------------------------------|
| 값 저장 방식     | 값 자체 저장                  | 객체 주소(참조값) 저장             |
| 예시 타입        | int, double, boolean, char    | String, Scanner, 배열, 사용자 클래스 |
| 저장 위치        | 스택(Stack)                   | 스택(참조값) + 힙(객체 실제 데이터)  |
| 복사 시 동작     | 값 복사 → 서로 독립           | 주소 복사 → 같은 객체를 참조        |
| 메모리 크기      | 고정 크기 (예: int는 4byte)    | 객체 크기에 따라 다름               |
| 사용 목적        | 간단한 데이터 처리            | 객체 속성과 기능 사용              |

### 문자열 초기화할 때 적합한 방법
- 대부분의 경우엔 null보단, ""로 초기화하는 것이 적합함. (null에 +"문자열"하였을 때, String 값은 null문자열 이런식으로 나오기 때문)

### 클래스의 멤버 변수와 메서드 매개변수의 관계 정리
1. 멤버 변수와 지역 변수의 이름이 다를 경우
✔ this 없이도 접근 가능
✔ 메서드 내부에서 멤버 변수를 수정할 때 그대로 할당 가능
- 예시 코드
```java
public class Example {
    private int level; // 멤버 변수

    public void setLevel(int newLevel) { // 지역 변수 (이름이 다름)
        level = newLevel; // `this` 없이 할당 가능
    }
}```
2. 멤버 변수와 지역 변수의 이름이 같을 경우
✔ 지역 변수가 우선 참조됨 → 멤버 변수에 값이 반영되지 않음
✔ 멤버 변수를 수정하려면 this.level = level;을 사용해야 함
```java
public class Example {
    private int level; // 멤버 변수

    public void setLevel(int level) { // 지역 변수 (같은 이름)
        this.level = level; // `this`를 사용해 멤버 변수에 할당
    }
}```
3. 멤버 변수를 메서드의 매개변수로 직접 전달하려는 경우
✔ 만약 이름이 같다면 this.level을 사용해야 정확한 변수 전달 가능
```java
public class Example {
    private int level = 10;

    public void updateLevel(int level) {
        processLevel(this.level); // `this.level`로 멤버 변수 전달
    }

    private void processLevel(int level) {
        System.out.println("처리된 level 값: " + level);
    }
}```

💡 최종 정리
- ✅ 이름이 다르면 this 없이도 멤버 변수 접근 가능
- ✅ 이름이 같으면 this.level을 사용해야 멤버 변수를 정확히 참조 가능
- ✅ 멤버 변수를 메서드의 매개변수로 직접 전달하려면 this.level을 명시적으로 사용해야 안전함

자바의 printf는 % 기호 다음에 정해진 형식 문자 (d, f, s, 등)가 나와야 하는데, "%d%)"와 같은 경우에는 ')'를 서식 문자로 오해하기 때문에, %기호를 출력하고 싶다면, %%를 사용해야 함.

또한 정수를 나누기 할 땐, 나누는 수가 더 크면 무조건 0이 되므로, 정확한 값을 계산하고 싶다면, double로 형변환을 해주거나, 정수에 1.0을 곱해주는 것이 좋다. 