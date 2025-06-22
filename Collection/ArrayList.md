+ List와 ArrayList의 가장 큰 차이점은 **List는 인터페이스(Interface)이고, ArrayList는 List 인터페이스를 구현한 클래스(Class)**라는 점

- ArrayList is a parameterized class임.
Parameterized class has a parameter which is a type.

제네릭(Generic) 또는 parameterized class란
“자료형(type)”을 나중에 결정할 수 있도록 만드는 클래스나 메서드야.

Parameterized class란?
클래스가 **제네릭 타입 매개변수(T)**를 받아서
그에 따라 동작하는 구조라면 → parameterized class라고 해.

즉, "제네릭을 사용하는 클래스 = 파라미터화된 클래스"
👉 같은 의미임

- List 인터페이스를 구현하므로 다양한 메서드 사용 가능 (add, remove, get, size, contains, ..)
- 순서를 유지하고 중복을 허용함.

+ 주의점: 내부적으로 배열을 사용하므로, 중간 삽입/삭제는 느릴 수 있음 (LinkedList가 더 적합)
