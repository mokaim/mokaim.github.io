---
layout : post
title : Spring Boot Junit Test에서 Autowired를 써서 NullpointException이 생긴다면!
comments : true
---

> ## Environments
>> #### SpringBoot 1.5.9
>> #### Java 1.8






.


<script src="https://gist.github.com/mokaim/3f5d4d23aaf0abcf82156c10c0b2b9d6.js"></script>
.

우선 src/test/java 밑에 빈으로 등록 할 Testl Class 를 생성해줍니다.

.
<script src="https://gist.github.com/mokaim/c3964d442b47f9400f2ed1a0c794d469.js"></script>


그리고 똑같은 경로인 src/test/java 밑에 실행시킬 Test Class 를 만듭니다.


![SpringBoot-Junit_01](/imgs/SpringBoot-Junit_01/SpringBoot-Junit_01.png)


스프링 부트에서 Autowired Annotation 으로 의존성을 주입하고 주입된 객체를 참조할 때 NullpointException이 발생하였습니다.


이유는 뭔지 모르겠으나 중요한 건 스프링에서 Autowired 를 Junit에서 테스트 할 경우 별도의 xml설정파일이 필요한데
스프링 부트에서는 xml을 잘 사용하지 않으므로... Autowired 를 쓰지못하는걸로 알았으나

어떻게든 구글링을 해보니 방법을 찾게 되었습니다.



@RunWith(SpringRunner.class)

@SpringBootTest


<script src="https://gist.github.com/mokaim/5467dc280ef5f42803b1c77ed77c7cbb.js"></script>



이 두 개 Annotation을 적는다면 스프링 부트 프로젝트의 Junit Test case에서 Autowired 로 의존성 주입을 하실 수 있겠습니다





출저 : https://www.bswen.com/2018/04/java-spring-boot-unit-test-NullPointerException.html
