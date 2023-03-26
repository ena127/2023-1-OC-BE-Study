[학습과제]

1. MVC 패턴이란?
2. API와 서버?
- 아무 API나 사용해보길 권장 (필수 아님)
1. RESTful 이란?

*spring boot - 아직 만들고 있는 version. 정식 아님

*dependencies - 어떤 라이브러리를 끌어 올 것인가? thymeleaf: html같은 화면 구성을 만들어 주는 

정적 컨텐츠 - 파일을 그냥 웹브라우저에 내려줌

MVC와 템플릿 엔진 - 서버에서 변형을 해서 내려줌

# 정적 컨텐츠

스프링 부트는 정적컨텐츠를 자동으로 제공함. 바로 웹 브라우저에 내려줌.

# MVC와 템플릿 엔진

## MVC pattern

**MVC: Model, View, Controller의 약자,  3가지 형태로 구분하여 개발하는 소프트웨어 개발 방법**

view는 화면을 그리는 데에 모든 역량을 집중함.

model, controller는 비즈니스 로직이나 내부적인것을 처리하는데에 집중함.

정확히는 model은 어플리케이션이 무엇을 할것인지 정의. 내부 비지니스 로직을 처리하기 위한 역할을 함. 

controller는 모델이 어떻게 처리할 지를 알려주줌. 모바일에서는 화면의 로직 처리 부분. 화면에서 사용자의 요청을 받아서 처리되는 부분을 구현하고, 요청 내용을 분석해서 Model과 View에 업데이트 요청.

view는 화면만, 비즈니스 로직이나 서버와 관련된 것은 controller만 하게함. 그리고 model에 화면과 관련된 것들을 넘겨줘서 처리.

*controller와 view를 쪼개는것이 기본.

### 특징

- 비지니스 처리 로직과 사용자 인터페이스 요소들을 분리시켜 서로 영향없이 개발 하기 수월함

# API & SERVER

## API

Application Programming Interface의 약자

정적 컨텐츠 방식을 제외하면, MVC방식에서 view를 찾아서 템플릿 엔진을 통해 html을 웹브라우저에 넘겨주는 방식이 있고, 그 외에 API 방식이 있다.

## SERVER

API 구조는 일반적으로 클라이언트와 서버 측면에서 설명됨. 요청을 보내는 애플리케이션을 클라이언트라고 하고 응답을 보내는 애플리케이션을 서버라고 함. 

### @ResponseBody를 이용한API

- 기본 문자 처리 - StringHttpMessageConverter
- ‘@ResponseBody’를 이용하면 http의 body에 문자 내용을 직접 반환함
- viewResolver 대신에 HttpMessageConverter동작.
- 기본 객체 처리 - MappingJackson2HttpMessageConverter

### RESTful API

Representational State Transfer의 약자.

REST는 클라이언트가 서버 데이터에 액세스하는 데 사용할 수 있는 GET, PUT, DELETE 등의 함수 집합을 정의. 

RESTful API는 두 컴퓨터 시스템이 인터넷을 통해 정보를 안전하게 교환하기 위해 사용하는 인터페이스.

클라이언트와 서버는 HTTP를 사용하여 데이터를 교환.

- REST API의 주된 특징: 무상태
- 무상태는 서버가 요청 간에 클라이언트 데이터를 저장하지 않음을 의미
- 서버에 대한 클라이언트 요청은 웹 사이트를 방문하기 위해 브라우저에 입력하는 URL과 유사. 서버의 응답은 웹 페이지의 일반적인 그래픽 렌더링이 없는 일반 데이터.

### RESTful API의 이점

- REST API를 구현하는 시스템은 REST가 클라이언트-서버 상호 작용을 최적화하기 때문에 효율적으로 크기를 조정할 수 있음.
- RESTful 웹 서비스는 완전한 클라이언트-서버 분리를 지원. 각 부분이 독립적으로 발전할 수 있도록 다양한 서버 구성 요소를 단순화하고 분리.
- REST API는 사용되는 기술과 독립적이므로, API 설계에 영향을 주지 않고 다양한 프로그래밍 언어로 클라이언트 및 서버 애플리케이션을 모두 작성할 수 있음. 또한 통신에 영향을 주지 않고 양쪽의 기본 기술을 변경 가능.

# JSON

객체가 반환이 되면, 기본 디폴트가 json방식으로 데이터를 만들어서 http에 반환함.

문자가 오면→ spring converter동작

객체가 오면 → Json converter동작