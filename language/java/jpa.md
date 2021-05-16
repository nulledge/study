# 들어가기 앞서

JPA를 이해하기 앞서 영속성의 개념을 이해해야 한다.
그런 다음 자바에서 영속성을 다루는 방법인 JDBC, SQL 맵퍼, ORM, JPA를 순서대로 이해한다.

# 개념

## 영속성

영속성(Persistence)는 프로그램이 종료되더라도 데이터가 보존되는 성질이다.
- 메모리에 저장된 데이터는 영속성이 없다. 따라서 프로그램을 종료하면 데이터도 함께 소실된다.
- 파일 시스템, 데이터베이스에 저장된 데이터는 영속성이 있다. 따라서 프로그램을 종료하고 다시 실행해도 데이터를 재사용 가능하다.

# 자바에서 영속성 부여하기

자바는 데이터베이스를 통해 영속성을 부여할 때 JDBC API를 사용한다.
최근에는 JDBC API를 직접 사용하는 대신 사용성을 개선한 SQL 맵퍼, ORM, JPA을 사용한다.

## JDBC API

JDBC(Java DataBase Connectivity) API는 '자바-데이터베이스 연결'이라는 이름에서 짐작할 수 있듯이 자바에서 데이터베이스를 사용하기 위한 명령어를 제공한다.
JDBC API는 Java SE 1.1에 도입된 표준으로 `java.sql`과 `javax.sql` 자바 패키지에 연관 클래스가 있다.
JDBC API는 명령어 인터페이스와 데이터베이스 드라이버를 분리했기 때문에 드라이버만 교체해서 다른 데이터베이스를 이용할 수 있다.

## SQL 맵퍼

JDBC API를 사용하는 개발자는 직접 SQL을 다뤄야 한다. SQL 맵퍼는 이 과정에서 사용성을 높여주는 기술이다. 자바 표준은 아니며, 구현체로 Mybatis가 있다.

### Mybatis

마이바티스는 XML에 SQL 질의문을 작성한다. 자바 코드에서 SQL 질의문을 가져가서 재활용한다.
예전에는 아이바티스(ibatis)라는 이름이었다.

## ORM

ORM(Object-Relational Mapping), 객체-관계 연결은 자바 객체(Object)와 관계형 데이터베이스(Relational DataBase)의 데이터를 자동으로 연결해주는 기술이다.
자바 클래스는 관계형 데이터베이스의 테이블에, 자바 클래스 객체는 관계형 데이터베이스의 테이블 열에 대응한다.

## JPA
JPA(Java Persistent API)는 Java EE에 도입된 ORM 표준 인터페이스로, `javax.persistence` 자바 피키지에 연관 인터페이스가 있다. Spring JPA, Hibernate를 비롯해 다양한 구현체가 있다.

## JDBC API, SQL 맵퍼, JPA 비교
- JDBC API : 개발자가 SQL을 직접 사용한다. 또한 자바 클래스와 데이터베이스 스키마를 별도로 작성해야 한다.
- SQL 맵퍼 : 개발자가 SQL을 직접 사용한다. JDBC API에 비교하면 사용성이 개선된다.
- JPA : 내부적으로 JDBC API를 사용하지만 개발자가 SQL을 직접 사용하지 않는다. 자바 명령어를 SQL로 자동으로 변환한다. 또한 자바 클래스를 작성하면 데이터베이스 스키마도 자동으로 생성된다.

# 참고
[위키피디아 - JDBC](https://en.wikipedia.org/wiki/Java_Database_Connectivity)
[위키피디아 - JPA](https://en.wikipedia.org/wiki/Jakarta_Persistence)
[Heee's Development Blog - ORM이란](https://gmlwjd9405.github.io/2019/02/01/orm.html)
[Heee's Development Blog - JDBC, JPA/Hibernate, Mybatis 차이](https://gmlwjd9405.github.io/2018/12/25/difference-jdbc-jpa-mybatis.html)
[Heee's Development Blog - JPA란](https://gmlwjd9405.github.io/2019/08/04/what-is-jpa.html)