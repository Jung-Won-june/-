# -전자정부프레임워크

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/c771da50-3bba-4b20-80fe-0c82972917bc/Untitled.png)

개발환경

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/20497314-09be-446d-95d0-5d247041e141/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/f1c3d74c-3509-4c57-83a4-d33ac416b6d7/Untitled.png)

먼저 C:파일 내부에 egovFrame_64bit 압축해제 후 eclipse.edu실행
textbook파일 내부 개발환경 내부 개발환경 교육교재- 서버 개발환경 구성 내용 적용
서버 개발환경 구성-Visual SVN Server설치

nexus서버실행 포트8081 bat파일 실행후 localhost실행 결과 화면. 

Jenkins서버실행

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/cbcd0291-8f14-4b19-9015-5944ba36b0a8/fcd452c4-07a7-4d3d-91eb-ba1b81c172df.png)

https://m.blog.naver.com/brilliantjay/221783505618 참고.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/d945cc8a-31de-4d52-964b-3ad9f25442e3/f6fcf77c-d036-435b-a551-f38718090c56.png)

초기 비밀번호는 secret파일에 존재.
[https://velog.io/@dudqls5271/서버셋팅-jenkins설치](https://velog.io/@dudqls5271/%EC%84%9C%EB%B2%84%EC%85%8B%ED%8C%85-jenkins%EC%84%A4%EC%B9%98) 참고.

초기 비밀번호가 nexus는 안빡세네. jenkins는 조금 빡세고.

5/5 전자정부프레임워크 공부

목적: 게시판을 효율적으로 최소화하여 만들 수 있는 장치가 무엇인가 탐색.
첫번째로 MSA 실습 환경 구성이라는 책자가 눈에 들어옴. micro service architecture이라고 하네요.

Spring 클라우드 개발환경에서 이루어지는 인증/인가 api, 프론트, 백엔드 협동

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/9b98fcb5-ea79-4432-9e2b-d0a11454cc87/Untitled.png)

게시판 제작을 위해 REST api이용 SPRING프레임워크 웹서비스 구축하기 실험.

REST란? 네트워크 구조 원리의 모음. 리소스를 정의하고 자원에 대한 주소를 지정하는 방법에 대한 조건들을 의미. 

RESTful의 요건

1. 클라이언트와 서버는 웹의 일관된 인터페이스를 따른다는 전제 하에 독립적으로 구현되어야 한다.
2. 균일한 인터페이스. 같은 인터페이스 제약에 따라 자원 식별, 자원 처리, 메시지, HATEOAS가 상호 운영되어야 한다.
3. 계층 시스템. 웹의 인터페이스 이용해 프락시, 게이트웨이 같은 네트워크 기반 중간매체 사용가능해야 함.
4. 캐시 처리. 웹 서버가 응답 데이터마다 캐시 여부를 선언할 수 있어야 한다.
5. 무상태. 웹 서버가 클라이언트 상태 관리 필요 없음.
6. 주문형 코드. 선택사항인 스크립트나 플러그인 같은 어플리케이션을 클라에 전송하여 클라가 실행할 수 있도록 해야 한다.

자원 표현, 메소드

결국 api api하는 이유는 데이터 형식의 표준을 정의하고, 그것을 이용하는 것이기 때문이다. 
REST api는 URI(Uniform Resource Identifier) 경로를 사용하여 자원을 나타내고, 슬래시(/)로 경로 구분한다.

간단하게 https://www.bookstore.com/books/1 이렇게 자원 표현한다. 이 자원에 대한 행위를 나타내야 하는데, CRUD(Create, Read, Update, Delete) 상태는 URI에 표현되지 않고 HTTP 프로토콜 사용한다. 이를 POST, GET, PUT, DELETE 등 메소드를 이용해 처리한다.

이제 웹 애플리케이션의 종류 중 Model1, Model2 중 두번째 요소를 알아볼 것인데, 이는 MVC라고 한다. Model, View, Controller 이렇게 세 영역으로 나누어지는 구조로 애플리케이션 설계.

![KakaoTalk_20240518_001735589.jpg](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/e4cd3739-11eb-4c3e-b267-c0840182acd8/a042192b-c29b-4524-badb-b6229d2b2a1d.png)

Model 영역은 JavaBean이고 App에서 사용하는 데이터를 다루거나 비즈니스 로직을 다룬다.

View 영역은 JSP이고 클라이언트에게 보이는 표현 영역으로 프레젠테이션 로직을 처리. 일반적으로 View 영역을 통해 HTML을 생성.

Control 영역은 Servlet이고 Model과 View 영역 간 흐름을 제어하는 역할. 클라이언트 요청을 받아 이를 처리하기 위한 Model을 호출하여 처리하고 그 결과를 View에게 전달. 어떤 모델과 어떤 뷰를 설정할지 전달해주는 컨트롤 타워 역할.

Spring MVC는 클라이언트로부터 요청 받아 DispatchServlet이라는 Front controller 이용 controller에게 전달. @Controller 어노테이션? 과 @RequestMapping 어노테이션?만으로 구현 가능. 또한 @PathVariable, @RequestBody, @ResponseBody 어노테이션 이용해 REST api 구현 가능.

Spring MVC는 REST 서비스 생성 위해 두 가지 방법 제공. ModelAndView 사용 or HTTPMessageConverter 사용. 이번엔 후자 위주로 REST생성.

실제 개발 목적

도서 정보 처리하는 REST API 제작. 조회, 등록, 수정, 삭제 기능 구현.
만약 게시판을 만들기 위해서라면 어떤 것이 가능해야 할까?

글을 올릴 수 있는 권한을 가진 클라이언트가 있을 것이고, 그들이 글을 등록, 수정, 삭제할 수 있고 모든 접근 가능한 클라이언트가 조회할 수 있어야 할 것이다. 이런 점에서 배경 View영역만 다르고 엇비슷함을 알 수 있음.

개발 환경

Java 6 이상
Maven 메이븐은 프로젝트 관리 도구
개발 프레임워크는 spring 3.2
Logback/SLF4J 는 로깅 라이브러리이다
MyBatis는 데이타베이스

Maven은 프로젝트 객체 모델(Project object model)이라는 개념을 바탕으로 의존성 관리, 생명 주기 관리 등 제공하는 프로젝트 관리 도구이다. 컴파일과 동시에 빌드?를 수행하고 테스트 수행, 서버로 디플로이?할 수 있는 환경 제공. 결국 컴파일, 링크, 테스트, 배포 다 한다는 뜻.

빌드란? 컴파일과 링크 과정을 의미.

(여기서 컴파일은 .java 파일을 .class 실행파일로 바꾸는 작업, 그 후 단위 테스트나 통합 테스트를 진행하여 코드가 알맞게 실행되는지 테스트 프레임워크 JUnit, TestNG 등을 사용. 다음 패키징을 하는데 컴파일된 코드와 다른 리소스를 결합하여 배포 가능한 형식으로 만든다. .jar .war이 그 형식. 마지막으로 생성된 패키지를 로컬, 원격 저장소에 배포하여 다른 시스템이나 개발자가 사용하도록 한다.)

디플로이? 는 배포를 말한다. 

의존성 관리?
이게 가장 중요한데, 의존성을 추가하면 해당 라이브러리를 저장소에서 자동으로 내려받는다. 내가 따로 내려받아 프로젝트에 추가할 필요 없이 의존성 선언만 하면 된다는 뜻.

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-web</artifactId>
        <version>5.3.10</version>
    </dependency>
</dependencies>
```

이런 식으로 maven 경우에는 pom.xml파일에 외부 라이브러리 의존성 선언.

Logback/SLF4J

애플리케이션 개발 시 중요한 것은 로그를 잘 남기는 것.
로그를 남겨야 에러가 발생했을 때 대응 가능.
Logback은 최신 로깅 라이브러리. SLF4J는 로깅 파사드 라이브러리로 로깅 요청을 기존에 존재하는 로깅 라이브러리로 전달하는 역할. 따라서 SLF4J를 사용하고 구현체를 Logback로 사용한다면 로그 출력 코드는 SLF4J를 사용하지만 실제 출력은 Logback을 통해 이루어짐.

사용하는 이유? 바로 SLF4J를 사용하지 않는다면 과거의 Log4j를 사용하다가 Logback이용하려면 코드를 싹 다 갈아엎어야 하기 때문! 사용하면 그러지 않아도 구현체만 바꿔주면 된다.

Logback의 가장 대표적인 기능은 설정 파일 자동 재로딩 기능이다. 운영 중에 로그를 보길 원한다면 서버를 중지시킬 필요 없고, 설정 파일만 변경하면 자동 반영된다.

Spring Framework 3.2이상

스프링 프레임워크는 IoC 컨테이너이다(Inversion of Control) 자바의 객체 생성, 의존 관계 관리하는 기능 제공. 이렇게 하면 자바 코드 내부에서 다른 객체를 생성하고 의존 관계를 설정하지 않고 설정 파일을 통해 객체를 생성하여 의존 관계를 설정할 수 있다. 결국 DI(Dependency Injection) 패턴을 지원. 객체 간 느슨한 결합 유지 가능.

AOP(관점 지향 프로그래밍) 가능. 공통 모듈(라이브러리)을 여러 코드에 쉽게 적용 가능. 트랜젝션, 보안, 로깅 등 여러 모듈(라이브러리)에서 공통으로 사용하는 기능을 분리해 각 모듈에 적용 가능.

보면 어노테이션 사용하는것도 AOP중 하나라고 할 수 있음.

### **AOP 애너테이션의 종류**

Spring AOP에서 주로 사용되는 애너테이션은 다음과 같습니다:

1. **@Aspect**: 클래스를 애스펙트로 정의합니다.
2. **@Before**: 메서드 실행 전에 실행될 어드바이스를 정의합니다.
3. **@After**: 메서드 실행 후에 실행될 어드바이스를 정의합니다.
4. **@AfterReturning**: 메서드가 정상적으로 실행된 후에 실행될 어드바이스를 정의합니다.
5. **@AfterThrowing**: 메서드 실행 중 예외가 발생한 후에 실행될 어드바이스를 정의합니다.
6. **@Around**: 메서드 실행 전후 및 실행 중에 실행될 어드바이스를 정의합니다.

MyBatis 데이터베이스

데이터베이스 자원을 사용하기 위해 JDBC(Java Database Connectivity)를 이용해야 하고, 데이터 처리 작업을 한다. 이걸 더 간편하게 하는 것이 퍼시스턴스 프레임워크라고 한다.

Mybatis는 퍼시스턴스 프레임워크로, 개발자가 SQL, 저장 프로시저 등을 쉽게 사용하게 해준다.

크게 두 부분으로 이루어진다. 설정을 다루는 Configuration과 Mapper이 그것이다.

Configuration은 MyBatis에 대한 전반적 설정 정보를 가짐. XML 파일이나 Configuration클래스로 설정 가능. 
Mapper는 Mapper XML파일과 자바 Mapper Interface로 이루어진다. Mapper XML이 바로 SQL을 XML에 정의하는 것이다. 이렇게 DB에서 사용하는 자바와 SQL이 분리되도록 도와준다. 어노테이션을 이용해 Mapper Interface에 SQL을 직접 정의하는 기능도 존재.

개발 환경 구축하기

1. 메이븐으로 웹 애플리케이션 프로젝트 생성, 필요 의존성 추가

여기서 Eclipse IDE 사용해 New→Maven project생성. web-app설정까지 마치고 Group id와 Artifact id를 설정해야 함. 근데 이게 뭐지?

### **Group ID (`groupId`)**

**`groupId`**는 프로젝트를 그룹화하는 데 사용되는 고유 식별자입니다. 보통 조직의 도메인 이름을 역순으로 사용하여 고유성을 보장합니다. 예를 들어, **`com.example`**, **`org.apache`**, **`com.mycompany`** 등이 있을 수 있습니다. **`groupId`**는 Maven 프로젝트를 논리적으로 그룹화하며, 비슷한 프로젝트나 라이브러리를 함께 묶을 수 있습니다.

### **Artifact ID (`artifactId`)**

**`artifactId`**는 특정 프로젝트 또는 라이브러리를 식별하는 데 사용되는 고유 식별자입니다. 이는 주로 프로젝트 이름을 사용하며, 하나의 **`groupId`** 내에서 유일해야 합니다. 예를 들어, **`my-webapp`**, **`spring-core`**, **`junit`** 등이 있습니다.

이들은 모두 pom.xml파일 내부에 기록됨. com.jwjinit 이 Group id, springinit이 Artifactid임.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/563ed2e5-ac15-4c3a-8928-5ece16ea1bc5/ebb4715a-fd45-4904-90ed-218cd1efbf41/Untitled.png)

[INFO] project created from Old (1.x) Archetype in dir: C:\Users\proje\eclipse-workspace\springinit

결과물

pom.xml : 프로젝트에 대한 전반적인 정보

src/main/data : 자바 소스 파일 위치

src/main/resource : 배포할 리소스 파일 (XML, properties 등)

src/main/webapp : 웹 어플리케이션 관련 파일(web.xml 등)이 위치

src/test/java: 테스트 케이스 자바 소스 파일 위치

src/test/resources: 테스트 케이스에 사용할 리소스 파일 위치

target: 빌드된 결과물

소스 코드 컴파일

mvn compile  →컴파일된 클래스 파일은 target/classes 디렉터리에 생성

테스트 클래스 실행

mvn test  →컴파일된 테스트 클래스들은 target/test-classes 디렉터리에 생성, 테스트 결과 리포트는 target/surefile-reports 디렉터리에 저장.

테스트 통과하면 배포 가능한 war파일 만든다.

mvn package →실행하면 패키징해서 결과물 형성. 성공적으로 완료된다면 target디렉터리에 springinit.war 파일 생성된 것 확인가능.

위에서 말햇듯 필요한 외부 라이브러리에 대한 정보를 pom.xml의 의존성 란에 적으면, 알아서 받아와준다.
