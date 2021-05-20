---
layout : post
title : LOG4J2.xml 의 위치(LOG4J2.xml Location)
comments : true
---

> # Log4j2_ConfigLation.xml 위치
>> * #### 현재 프로젝트의 classpath 경로 안에 넣어야한다.

Log4j2 Framework 를 처음 사용해보시는 분들을 위한 포스팅입니다.


개인적으로 Log4j2 프레임워크를 처음쓰면서 테스트를 해보아야 하는데 그러기 위해서는 Log4j2.xml 파일을 생성하여 출력설정을 하여야 하는데 xml파일을 어디에다 위치 시켜야 할지 몰라서 몇 시간 동안 헤매고 있었습니다.




알고보니 Classpath 경로안에 넣어두기만 하면 알아서 작동된다고 하더군요.


SpringFramework 같은 경우 자동적으로 resource 폴더를 classpath에 포함시켜주기에 개발자가 직접적으로 설정할 필요는 없습니다.





<script src="https://gist.github.com/mokaim/a96bfd61496d48216dc554ce42f49aa5.js"></script>


먼저 위와 같은 코드로 log4j2.xml 파일을 작성해봅시다.


그리고 현재의 classpath 를 확인해봅시다.


![log4j2_classpath](/imgs/log4j2_classpath.jpg)



<script src="https://gist.github.com/mokaim/104021d9b7f15d97429647396af44bb9.js"></script>



위와같이 classpath 내에서 src 폴더가 포함되어있는 것을 알 수 있습니다.

그렇다면 src 폴더 안에 작성한 log4j2.xml 파일을 넣어줍시다.


![log4j2_classpath_src](/imgs/log4j2_classpath_src.jpg)


위와 같이 src 폴더에 넣어주시고 package를 하나 만들고 새롭게 Logging을 테스트 해 볼 Main Class를 하나 만들어줍시다.



<script src="https://gist.github.com/mokaim/2a986c812e81937c1a6bedf1847e1e63.js"></script>



소스코드는 위와 같습니다.


후에 Run을 눌러 main 메소드를 실행해주신다면



     2020-05-20 10:56:03,159 DEBUG [main] mokaim.Main (Main.java:14) - debug message
     2020-05-20 10:56:03,160 INFO  [main] mokaim.Main (Main.java:22) - info message


위와 같은 메시지가 Console 에 출력된다면 성공적으로 Log4j2_ConfigLation.xml 을 적용하신겁니다.
