# 스프링

스프링(Spring)은 자바 프레임워크다.

## J2EE와 차이점

### JSR 관점

J2EE(Java 2 Platform, Enterprise Edition)는 서블릿(servlet)과 JSP(Java Server Page) 등 웹 어플리케이션 기능을 제공한다.
이 기능들은 각각이 독립적인 JSR(Java Specification Request)에 해당한다.
J2EE는 수많은 JSR을 포함하는 포괄적 JSR(umbrella JSR)를 만족한다.

스프링은 J2EE에서 일부 JSR만을 만족한다.

### 빈 관점

자바로 어플리케이션을 만들 때 자주 필요한 기능들이 있다.
그리고 수많은 개발자들이 똑같은 기능을 제작하는 것은 매우 비효율적이다.
이러한 발상에서 J2EE는 코드의 재사용성을 높이기 위한 JSR로서 EJB(Enterprise Java Bean)와 EJB 컨테이너를 제공한다.

J2EE는 분산처리, 트랜잭션 관리 등 자주 필요한 기능을 제공한다.
EJB는 J2EE의 기능을 사용해서 웹 어플리케이션 서비스를 제공한다.
EJB 컨테이너는 EJB와 J2EE 사이에서 통신을 돕는 인터페이스로 작동한다.
이 구조에서 개발자는 EJB만 작성하고, 다양한 J2EE 환경에서 동일한 웹 어플리케이션을 실행할 수 있다.

하지만 EJB에는 문제가 있었다. 편의성을 높이기 위한 EJB였지만, 역설적으로 J2EE 기능을 사용하기 위해서 EJB 자체가 복잡해졌다.
또한 제조사마다 J2EE에 추가적으로 제공하는 기능이 달라서, EJB를 새로 작성하는 경우도 있다.

이 문제를 해결하기 위해 스프링은 스프링 빈(Spring bean)을 사용한다.
스프링 빈은 EJB처럼 복잡하지 않고, 특정 제조사의 J2EE 추가 기능에 종속적이지 않는다.
다른 이름으로 `평범한 옛 자바 객체`라는 뜻처럼 POJO(Plain Old Java Object)라고 부른다.
EJB가 EJB 컨테이너를 통해 J2EE 기능을 사용하는 것처럼, 스프링 빈은 스프링 컨테이너를 통해 스프링 프레임워크의 기능을 사용한다.

## 주요 개념

### 제어 역전과 의존성 주입

### 스프링 컨테이너

### 스프링 빈

# 참고

- [Spring Framework Documentation, Spring](https://docs.spring.io/spring-framework/docs/current/reference/html/index.html)
- [Learning more about EJBs and the EJBContainer, IBM](https://www.ibm.com/support/pages/learning-more-about-ejbs-and-ejbcontainer)
- [스프링 개론, victolee](https://victorydntmd.tistory.com/158)
