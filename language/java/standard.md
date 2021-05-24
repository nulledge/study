# Java

자바는 자바 커뮤니티 프로세스(JCP, Java Community Process)라는 단체에서 언어 표준을 규정한다.
자바 언어 표준은 환경(platform), 버전(version)에 따라 구분된다.
자바 구현체는 목적(develop, runtime)과 제조사(Oracle, OpenJDK, ...)에 따라서 다시 구분된다.

## 표준

### 환경

자바는 환경별로 다른 기능을 제공한다.
- SE : Standard Edition. 기준이 되는 실행환경으로 데스크탑, 서버를 대상으로 한다.
- ME : Micro Edition. SE에서 한정된 자원을 사용하며 모바일, 임베디드 환경을 대상으로 한다.
- EE : Enterprise Edition. SE에서 웹 어플리케이션(서블릿, 자바 서버 페이지, 분산처리) 요소를 추가했다.
- Card : 스마트 카드 환경을 대상으로 한다.

### 버전

|	Version				|	Release date	|	End of Free Public Updates					|	Extended Support Until							|
|-----------------------|-------------------|-----------------------------------------------|---------------------------------------------------|
|	JDK Beta			|	1995			|	?											|	?												|
|	JDK 1.0				|	January 1996	|	?											|	?												|
|	JDK 1.1				|	February 1997	|	?       				                    |	?												|
|	J2SE 1.2			|	December 1998	|	?											|	?												|
|	J2SE 1.3			|	May 2000		|	?											|	?												|
|	J2SE 1.4			|	February 2002	|	October 2008								|	February 2013									|
|	J2SE 5.0			|	September 2004	|	November 2009								|	April 2015										|
|	Java SE 6			|	December 2006	|	April 2013									|	December 2018									|
|						|					|												|	December 2023, paid support for Zulu			|
|	Java SE 7			|	July 2011		|	April 2015									|	July 2022										|
|	Java SE 8 (LTS)		|	March 2014		|	January 2019 for Oracle (commercial)		|	December 2030									|
|						|					|	December 2030 for Oracle (non-commercial)	|													|
|						|					|	December 2030 for Zulu						|													|
|						|					|	At least May 2026 for AdoptOpenJDK			|													|
|						|					|	At least May 2026 for Amazon Corretto		|													|
|	Java SE 9			|   September 2017	|	March 2018 for OpenJDK						|	N/A												|
|	Java SE 10			|   March 2018		|	September 2018 for OpenJDK					|	N/A												|
|	Java SE 11 (LTS)	|   September 2018	|	September 2027 for Zulu						|	September 2026, or September 2027 for e.g. Zulu	|
|						|					|	At least October 2024 for AdoptOpenJDK		|													|
|						|					|	At least September 2027 for Amazon Corretto	|													|
|	Java SE 12			|   March 2019		|	September 2019 for OpenJDK					|	N/A												|
|	Java SE 13			|   September 2019	|	March 2020 for OpenJDK						|	N/A												|
|	Java SE 14			|   March 2020		|	September 2020 for OpenJDK					|	N/A												|
|	Java SE 15			|   September 2020	|	March 2021 for OpenJDK, March 2023 for Zulu	|	N/A												|
|	Java SE 16			|   March 2021		|	September 2021 for OpenJDK					|	N/A												|
|	Java SE 17 (LTS)	|   September 2021	|	September 2030 for Zulu						|	TBA												|

`Java SE x`는 `Java 1.x` 혹은 `Java 1.x.0`로 표기하기도 한다.
자주 사용하는 자바 버전은 LTS(Long Time Support, 장기간 지원 대상)인 8, 11이다.
8과 11의 차이점은 다양하지만 당장 체감할 만한 변화는 `var` 키워드 지원이다.

## 구현체

### 목적

자바 구현체는 목적별로 제공하는 기능이 다르다.
- JDK : Java Development Kit. 개발 목적으로 컴파일러 외 유용한 도구를 포함한다.
- JRE : Java Runtime Environment. 단순 실행 목적으로 개발용 도구를 제외했다.

### 제조사

자바 구현체는 제조사마다 제공하는 기능이 다르다.
- OpenJDK : 표준 Java SE 구현체.
- Oracle : 표준 Java SE의 기능뿐만 아니라 Oracle과 SUN의 유료 기능을 제공한다.

# 참고
[자바 이름 규칙](https://www.oracle.com/java/technologies/javase/jdk8-naming.html)
