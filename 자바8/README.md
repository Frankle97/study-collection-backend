## Optional 
````
if (study != null) {
    System.out.println();
}
````
우리는 숱하게 이러한 Null 체크를 진행하였다.<br/>
Optional 는 **오직 값 한 개가 들어있을 수 있고, 없을 수도 있는 컨테이너**를 의미한다.<br/>
Optional는 개발자에게 NPE 관리를 편하게 도와주는 도구이다.<br/>
Optional 은 값이 비싸다. 신중하게 사용해야 한다.

### 주의
리턴값으로 쓰는 것을 권장(파라미터, 키, 인스턴스 필드의 타입으로 사용하지 말 것)<br/>
Optional을 리턴하는 메서드에서 null 리턴하지 말 것<br/>
기본형 타입에 Optional 사용이 필요하다면 걺자는 OptionalInt, OptionalLong... 등을 사용할 것<br/>
Collection, Map, Stream, Array, Optional 은 Optional 로 Wrapping 금지

## 사용

**값이 있다면 값을 그대로 반환**<br/>
-   optional.isPresent();
    -   optional 값 여부 체크
    
-   optional.get();
    -   값을 가져옴, 없으면 NoSuchElementException
    
-   optional.orElse();
    -   값이 없을 경우 else 값을 반환
        - 참고 : 값이 있어도 else는 무조건 실행된다.
    
-   optional.orElseGet();
    -   값이 없을 경우 elseGet 값을 반환
        -   참고 : 값이 있으면 반환으로 끝난다. elseGet을 실행하지 않음
        -   팁 : orElse는 이미 존재한다면, elseGet은 새로 생성해야 한다면
    
-   optional.orElseThrow();
    -   값이 없을 경우 정의한 에러를 throw
    
---
### 기존 Date
기존 java.util.Date는 immutable하지 않으므로 thread-safe 하지 않았다. <br/>
클래스 이름과 메서드 명도 명확하지 않았다. 데이트 클래스의 getTime을 하는데 시간이 아닌 날짜를 반환하는등..<br/>

### 자바 8 DateTime
자바8에서 DateTime API는 Clear, Fluent, Immutable, Extensible를 철학으로 한다.<br/>
**Instant,**
**LocalDateTime,**
**ZonedDateTime**

기간 표현 방법
Period, Duration

레거시 Date API에서 자바8 DateTime API로의 변환이 자유롭다
