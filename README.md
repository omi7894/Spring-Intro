# Spring-Intro
✨인프런 김영한 스프링 입문 강의
<br/>

- 공통 
	- 스프링 빈 등록을 해주어야 한다.   
	- @Controller, @Service등 어노테이션 이용하기  
	- 자바코드로 직접 등록하기
 <br/>  

- domain 
	- 회원은 id와 Name을 갖는다.
<br/>

- repository
	- 인터페이스 : MemberRepository 
	- 클래스 : MemoryMemberRepository 
<br/>

- 단위 test
	- JUnit 이라는 프레임워크 사용  
	- MemoryMemberRepositoryTest 클래스   
	- @AfterEach를 통해 테스트가 끝날때마다 저장소를 clear하도록  
	- 테스트를 먼저만드는 개발 : 테스트 주도 개발(TDD)  
	- 실제코드에는 포함되지 않음 (한글써도됨)
<br/>

- service
	- 비즈니스 구현  
	- 우선 멤버repository 부터 선언  
<br/>

- 스프링빈과 의존관계
	- 회원컨트롤러가 회원서빗와 회원레포지토리를 사용할 수 있도록 의존관계 준비  
	- 생성자에 @Autowired -> 연관된 객체를 스프링 컨테이너에서 찾아서 넣어준다 == DI  
	  -> memberService가 스프링 빈으로 등록되어있어야 한다.  
	  -> @Controller @Service등 사용 or 자바코드로 직접 스프링 빈 등록(Spring Config에)  
<br/>

- DB
	- jdbc나 jpa 쓰기위해 build.gradle에 implementation 추가하고 나서 gradle refresh하기(코끼리 똑딱이)  
	- application.properties 에 DB 연결정보 설정
<br/>

- 통합 test
	- @Transactional을 통해 다음 테스트 진행하기전 db 롤백  
<br/>

- JPA  
	- JPA 사용할땐 EntityManager 사용  
	- Service에 @Transactional이 있어야 한다.  
<br/>  

- AOP
	- 관점지향프로그래밍  
	- 공통관심사항, 핵심관심사항 분리  
	- @Aspect  
	- @Around -> 어디에 적용할지  
	- jointPoint 사용  
	- 프록시 기술  
