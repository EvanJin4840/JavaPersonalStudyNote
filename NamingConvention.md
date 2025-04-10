### 🧾 Java Naming Conventions 요약

| 코드 요소     | 네이밍 규칙 (한글)                     | 예시                   | 권장 여부 |
|---------------|------------------------------------------|------------------------|------------|
| 변수명        | 소문자로 시작 + camelCase 사용          | `userName`, `age`      | ✅        |
| 메서드명      | 소문자로 시작 + camelCase 사용          | `getName()`, `print()` | ✅        |
| 클래스명      | 대문자로 시작 + PascalCase 사용         | `String`, `MyClass`    | ✅        |
| 상수명        | 모두 대문자 + 단어는 밑줄로 구분        | `MAX_VALUE`, `PI`      | ✅        |
| 변수명 대문자 시작 | 클래스와 혼동 우려 → 비권장           | `Name`, `String`       | ❌        |
| 예약어/타입명과 동일 | 혼란 유발 → 사용 지양                  | `String String = ...`  | ❌        |

💡 camelCase: 단어 첫 글자만 대문자 (userName)
💡 PascalCase: 모든 단어 첫 글자 대문자 (MyClass)
💡 UPPER_SNAKE_CASE: 모든 글자 대문자, 단어는 _로 구분 (MAX_VALUE)

## ✅ Summary

- Follow Java's standard naming conventions for clean, readable, and maintainable code.
- Avoid using uppercase variable names or reserved keywords as variable names.
- Use the correct style (`camelCase`, `PascalCase`, `UPPER_SNAKE_CASE`) depending on the code element.

---

> 📎 Tip: Tools like **Checkstyle** or **Google Java Style Guide** can help enforce consistent naming in large projects.
## ✅ Summary

- Follow Java's standard naming conventions for clean, readable, and maintainable code.
- Avoid using uppercase variable names or reserved keywords as variable names.
- Use the correct style (`camelCase`, `PascalCase`, `UPPER_SNAKE_CASE`) depending on the code element.

---
