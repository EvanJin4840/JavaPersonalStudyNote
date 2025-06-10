## StringTokenizer
* 자바에서 문자열을 *지정한 구분자(delimiter)*로 잘라서,
각 조각을 **토큰(token)**으로 분리해주는 유틸리티 클래스입니다.
즉, 긴 문자열을 공백, 콤마, 탭, 기타 기호 등 원하는 기준으로 쉽게 나눌 수 있게 해줍니다

### 주요 메서드
- hasMoreTokens() : 다음 토큰이 있는지 확인 (boolean 반환)
- nextToken() : 다음 토큰을 꺼내서 반환 (String 반환)
- countTokens() : 남은 토큰 개수 반환 (int 반환)

### 특징 및 활용
- split()과 차이: split()은 배열로 한 번에 반환, StringTokenizer는 반복문으로 하나씩 꺼내 씀
- 여러 구분자 사용: new StringTokenizer(str, ",|;!")처럼 여러 기호를 구분자로 지정 가능
- 기본 구분자: 공백, 탭, 줄바꿈 등
- 구분자 포함 여부: 세 번째 인자(boolean)로 구분자도 토큰에 포함시킬 수 있음