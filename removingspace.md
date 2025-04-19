# Java 문자열 공백 제거 요약

## ✅ 모든 공백(스페이스, 탭, 줄바꿈 등) 제거

```java
String input = "  Hello\tWorld \n Java  ";
String result = input.replaceAll("\\s+", "");
System.out.println(result);  // HelloWorldJava
```

## 🔍 정규표현식 설명

| 표현식 | 의미 |
|--------|------|
| `\\s`  | 공백 문자 (스페이스, 탭, 줄바꿈 등) |
| `+`    | 1개 이상 반복 |

---

## ✅ 특정 공백만 제거

| 목적         | 코드                                |
|--------------|-------------------------------------|
| 스페이스만 제거 | `str.replace(" ", "")`               |
| 탭만 제거      | `str.replace("\t", "")`              |
| 줄바꿈 제거    | `str.replaceAll("\\r?\\n", "")`      |

---

## ⚠️ 참고

- `replaceAll()`은 정규표현식을 사용함
- 앞뒤 공백만 제거하고 싶을 때는 `str.trim()` 또는 `str.strip()` 사용
- `str.trim()` 제거대상 : ASCII 공백만 (U+0020) [공백 코드값이 32(' ')일 때만 제거]
-  `str.strip()` 제거대상 : 유니코드 공백 전체 [Character.isWhitespace() 사용]