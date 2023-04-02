### 웹 애플리케이션의 구조

일반적인 웹 애플리케이션의 구조는 컨트롤러, 서비스, 리포지토리, 그리고 도메인 객체, DB로 구성됨.

컨트롤러 - 웹 MVC의 컨트롤러 역할

- 개발한 기능을 실행해서 테스트 할 때 자바의 main 메소드를 통해 실행하거나 웹 애플리케이션의 컨트롤러를 통해서 해당 기능을 실행함. ⇒ 실행 시 오래걸리고, 반복실행이 어려우며 여러 테스트를 한번에 실행하기 어려움.

서비스 - 핵심 비즈니스 로직 구현 ex) 회원은 중복가입이 안됨.

리포지토리 - 데이터베이스에 접근, 도메인 객체를 DB에 저장하고 관리

도메인 - 비즈니스 도메인 객체 ex)회원, 주문, 쿠폰 등을 데이터베이스에 저장하고 관리

### 클래스 의존 관계

회원 비즈니스 로직에는 회원 서비스가 있고, 회원 리포지토리는 인터페이스로 설계함. 아직 데이터 저장소가 선정되지 않았기 때문. 

회원 리포지토리를 인터페이스로 만들고 구현체를 메모리 구현체로 만듦. 메모리로 단순하게 저장할 수 있도록 함. 구체적인 구현체가 선정되면 그 때 인터페이스로 변경할 수 있도록 함.

### TDD

TDD : Test-driven Development의 약자. 매우 짧은 개발 프로세스를 반복하는 소프트웨어 개발 프로세스 중 하나.

**테스트를 먼저 만들고 구현 클래스를 만들어서 작동시켜 보는 것.**

장점 1. 테스트 코드를 먼저 작성함으로써 좀 더 명확한 기능과 구조를 설계할 수 있음. 각각의 함수를 정의할 때 각 기능들에 대해 철저히 구조화 시켜 코드를 작성할 수 있게 됨. **모든 코드를 재사용할 것을 염두에 두고 개발하기 때문에 보다 더 객체지향적인 개발이 가능함**.

2. 테스트 케이스를 미리 고려해보며 작성하기 때문에 **설계 오류 시 수정시간이 단축됨**
3. **디버깅 시간 단축** - 기본적으로 **단위 테스트 기반의 테스트 코드를 작성**하기 때문에 각각의 모듈별로 테스트를 진행해보면 문제 지점을 쉽게 알아볼 수 있음.