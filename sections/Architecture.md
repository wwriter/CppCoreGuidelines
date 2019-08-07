
# <a name="S-A"></a>A: 설계(Architectural) 아이디어

이 절은 보다 고수준의 구조와 라이브러리에 대한 아이디어를 포함한다.

구조적 아이디어 규칙 요약:

* [A.1: 코드에서 안정적인 부분과 그렇지 않은 부분을 분리시켜라](#Ra-stable)
* [A.2: 잠재적으로 재사용 가능한 부분을 라이브러리로 표현하라](#Ra-lib)
* [A.4: 라이브러리 간 순환관계가 있어서는 안된다](#?Ra-dag)
* [???](#???)
* [???](#???)
* [???](#???)
* [???](#???)
* [???](#???)
* [???](#???)

### <a name="Ra-stable"></a>A.1: 코드에서 안정적인 부분과 그렇지 않은 부분을 분리시켜라

코드에서 상대적으로 안정성이 낮은 부분을 분리시키면 유닛 테스트 및 유지보수( 인터페이스 개선, 리팩토링, 일부분 제거... )가 용이해진다.

### <a name="Ra-lib"></a>A.2: 잠재적으로 재사용 가능한 부분을 라이브러리로 표현하라

##### Reason

##### Note

A library is a collection of declarations and definitions maintained, documented, and shipped together.
A library could be a set of headers (a "header only library") or a set of headers plus a set of object files.
A library can be statically or dynamically linked into a program, or it may be `#include`d

### <a name="Ra-dag"></a>A.4: 라이브러리 간 순환관계가 있어서는 안된다

##### Reason

* A cycle implies complication of the build process.
* Cycles are hard to understand and may introduce indeterminism (unspecified behavior).

##### Note

A library can contain cyclic references in the definition of its components.
For example:

    ???

However, a library should not depend on another that depends on it.

