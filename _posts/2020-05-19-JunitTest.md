---
layout : post
title : Junit 이란
comments : true
---

> # Junit 이란 오픈소스 단위 테스트 개발도구입니다.

    Junit은 외부 테스트 프로그램(Junit Case class)를 작성하여 일일히 개발자가
    System.out.print 등으로 디버깅할 필요없이 더욱 효율적으로 테스트 코드를 작성할 수 있겠습니다.
    프로그램 테스트 중 걸리는 시간 역시 측정이
    가능하며 Eclipse에서 기본적으로 사용가능 합니다.
    규모가 큰 프로젝트 같은 경우에는 단위테스트가 반드시 필요합니다. JUnit은 보이지 않는 단위테스트를 끌어내어
    정형화시켜 단위테스트를 쉽게 해주는 테스트용 Framework 입니다.
    JDK 1.4에서 추가된 assertXXX를 사용하여 Test를 진행합니다.
    JUnit은 테스트 결과를 확인하는 것 이외 최적화된 코드를 유추해내는 기능도 제공합니다.
    또한 테스트 결과를 단순한 텍스트로 남기는 것이 아니라 Test Class 로 남깁니다.
    그래서 개발자에게 테스트 방법 및 클래스의 History를 넘겨줄 수도 있습니다.

> # 특징
* #### 단위 테스트 Framework 중 하나
* #### 문자 혹은  GUI기반으로 실행
* #### 단정문으로 테스트 케이스의 수행 결과를 판별(assertEquals(prediction value, real value))
* #### Annotaion 으로 간결하게 지원
* #### 결과는 성공(Green color), 실패(red color) 중 하나로 표시


> # Eclipse에서 Junit 테스트 해보기

![JUnit_01](/assets/JUnit_01.png)


     우선 Project Exporer 에서 우측 마우스 클릭 - > 새로운 기본 자바프로젝트를 엽니다.


![JUnit_02](/assets/JUnit_02.png)


     프로젝트 이름은 간략하게 JUnitTest 라고 지어줍시다.


![JUnit_03](/assets/JUnit_03.png)


     그리고 패키지를 만들어주시고 새로운 Class 를 생성합니다.
     저는 간단히 더하기 빼기 메소드를 가진 Class 를 구현해보겠습니다.
     Class는 Calculator 의 약자인 Cal 로 지정하겠습니다.


![JUnit_04](/assets/JUnit_04.png)

*

<div class="colorscripter-code" style="color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; width:600px; height:300px; position:relative !important;overflow:auto"><table class="colorscripter-code-table" style="margin:0;padding:0;border:none;background-color:#fafafa;border-radius:4px;" cellspacing="0" cellpadding="0"><tr><td style="padding:6px 0;text-align:left"><div style="margin:0;padding:0;color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important;line-height:130%"><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">package</span>&nbsp;io.github.mokaim.test;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">public</span>&nbsp;<span style="color:#ff3399">class</span>&nbsp;Cal&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ff3399">public</span>&nbsp;Cal()&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#999999">//&nbsp;TODO&nbsp;Auto-generated&nbsp;constructor&nbsp;stub</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;}</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ff3399">public</span>&nbsp;<span style="color:#0099cc">int</span>&nbsp;<span style="color:#0099cc">add</span>(<span style="color:#0099cc">int</span>&nbsp;a,&nbsp;<span style="color:#0099cc">int</span>&nbsp;b)&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ff3399">return</span>&nbsp;a&nbsp;<span style="color:#0086b3"></span><span style="color:#ff3399">+</span>&nbsp;b;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;}</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ff3399">public</span>&nbsp;<span style="color:#0099cc">int</span>&nbsp;sub(<span style="color:#0099cc">int</span>&nbsp;a,&nbsp;<span style="color:#0099cc">int</span>&nbsp;b)&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ff3399">return</span>&nbsp;a&nbsp;<span style="color:#0086b3"></span><span style="color:#ff3399">-</span>&nbsp;b;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;}</div><div style="padding:0 6px; white-space:pre; line-height:130%">}</div></div><div style="text-align:right;margin-top:-13px;margin-right:5px;font-size:9px;font-style:italic"><a href="http://colorscripter.com/info#e" target="_blank" style="color:#e5e5e5text-decoration:none">Colored by Color Scripter</a></div></td><td style="vertical-align:bottom;padding:0 2px 4px 0"><a href="http://colorscripter.com/info#e" target="_blank" style="text-decoration:none;color:white"><span style="font-size:9px;word-break:normal;background-color:#e5e5e5;color:white;border-radius:10px;padding:1px">cs</span></a></td></tr></table></div>

*

     위와 같은 간단한 더하기 빼기 메소드를 작성해 봅시다.

![JUnit_05](/assets/JUnit_05.png)


     그리고 Package에서 우측 마우스 클릭 후 JUnit Test Case 를 클릭해줍시다.


![JUnit_06](/assets/JUnit_06.png)


     그러면 위와 같은 화면이 등장하게됩니다.


![JUnit_07](/assets/JUnit_07.png)

     Package 이름과 밑의 Class under test 이름을 작성해줍시다.
     이름은 Test를 진행할 Class Name + Test 로 작성해주시면 됩니다.
     저는 CalTest 로 작성하도록 하겠습니다.
     Class under test 는 테스트를 실행할 Class 가 되겠습니다.
     지금과 같은 경우는 방금 생성하였던 Cal Class 를 선택해주시면 되겠습니다.


![JUnit_08](/assets/JUnit_08.png)

     위와 같이 자신의 Package 이름을 검색하면 테스트 가능한 Class를 보여줍니다.

![JUnit_09](/assets/JUnit_09.png)

     확인을 클릭해줍니다.

![JUnit_10](/assets/JUnit_10.png)

     만일 위와같은 화면이 나온다면 OK를 눌러줍시다.
     이유인 즉슨 Eclipse 에서 기본적으로 JUnit 프레임워크 라이브러리를 지원해주지만
     지금 만든 프로젝트에서는 아직까지 Eclipse 의 JUnit 라이브러리를 불러오지 않아서
     나오는 메시지 입니다.

![JUnit_11](/assets/JUnit_11.png)


*
<div class="colorscripter-code" style="color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; width:600px; height:300px; position:relative !important;overflow:auto"><table class="colorscripter-code-table" style="margin:0;padding:0;border:none;background-color:#fafafa;border-radius:4px;" cellspacing="0" cellpadding="0"><tr><td style="padding:6px 0;text-align:left"><div style="margin:0;padding:0;color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important;line-height:130%"><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">package</span>&nbsp;io.github.mokaim.test;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">import</span>&nbsp;<span style="color:#ff3399">static</span>&nbsp;org.junit.jupiter.api.Assertions.<span style="color:#0086b3"></span><span style="color:#ff3399">*</span>;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">import</span>&nbsp;org.junit.jupiter.api.Test;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">class</span>&nbsp;CalTest&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;@Test</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ff3399">void</span>&nbsp;test()&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fail(<span style="color:#993333">"Not&nbsp;yet&nbsp;implemented"</span>);</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;}</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">}</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div></div><div style="text-align:right;margin-top:-13px;margin-right:5px;font-size:9px;font-style:italic"><a href="http://colorscripter.com/info#e" target="_blank" style="color:#e5e5e5text-decoration:none">Colored by Color Scripter</a></div></td><td style="vertical-align:bottom;padding:0 2px 4px 0"><a href="http://colorscripter.com/info#e" target="_blank" style="text-decoration:none;color:white"><span style="font-size:9px;word-break:normal;background-color:#e5e5e5;color:white;border-radius:10px;padding:1px">cs</span></a></td></tr></table></div>

*


     그럼 위와같은 코드가 생성됨을 알 수 있습니다.

![JUnit_12](/assets/JUnit_12.png)

*

<div class="colorscripter-code" style="color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; width:600px; height:300px; position:relative !important;overflow:auto"><table class="colorscripter-code-table" style="margin:0;padding:0;border:none;background-color:#fafafa;border-radius:4px;" cellspacing="0" cellpadding="0"><tr><td style="padding:6px 0;text-align:left"><div style="margin:0;padding:0;color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important;line-height:130%"><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">package</span>&nbsp;io.github.mokaim.test;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">import</span>&nbsp;<span style="color:#ff3399">static</span>&nbsp;org.junit.jupiter.api.Assertions.<span style="color:#0086b3"></span><span style="color:#ff3399">*</span>;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">import</span>&nbsp;org.junit.jupiter.api.Test;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#ff3399">class</span>&nbsp;CalTest&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;@Test</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#ff3399">void</span>&nbsp;test()&nbsp;{</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Cal&nbsp;cal&nbsp;<span style="color:#0086b3"></span><span style="color:#ff3399">=</span>&nbsp;<span style="color:#ff3399">new</span>&nbsp;Cal();</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cal.<span style="color:#0099cc">add</span>(<span style="color:#308ce5">10</span>,&nbsp;<span style="color:#308ce5">5</span>);</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cal.sub(<span style="color:#308ce5">10</span>,&nbsp;<span style="color:#308ce5">5</span>);</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;assertEquals(<span style="color:#308ce5">15</span>,&nbsp;cal.<span style="color:#0099cc">add</span>(<span style="color:#308ce5">10</span>,&nbsp;<span style="color:#308ce5">5</span>));</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;assertEquals(<span style="color:#308ce5">5</span>,&nbsp;cal.sub(<span style="color:#308ce5">10</span>,&nbsp;<span style="color:#308ce5">5</span>));</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;}</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">}</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div></div><div style="text-align:right;margin-top:-13px;margin-right:5px;font-size:9px;font-style:italic"><a href="http://colorscripter.com/info#e" target="_blank" style="color:#e5e5e5text-decoration:none">Colored by Color Scripter</a></div></td><td style="vertical-align:bottom;padding:0 2px 4px 0"><a href="http://colorscripter.com/info#e" target="_blank" style="text-decoration:none;color:white"><span style="font-size:9px;word-break:normal;background-color:#e5e5e5;color:white;border-radius:10px;padding:1px">cs</span></a></td></tr></table></div>

*

     위와 같은 코드로 재작성 해봅니다.
     assertEquals 는 JUnit 에서 지원하는 메소드인데 사용자가 만든 메소드의 결과값이
     좌측의 예상값과 비교하여 예상값과 맞아떨어지지 않는다면 Junit 에서 False 처리되게끔
     합니다.
     한 마디로 객체 a,b가 같은 것인지 확인합니다.

![JUnit_13](/assets/JUnit_13.png)

     그리고 만들어진 Test Class에 마우스 우측 버튼 클릭 후 Run As - JUnit Test 를 클릭해줍니다.

![JUnit_14](/assets/JUnit_14.png)

     정상적으로 실행이 완료되면 위와 같이 초록색으로 완료표시가 나타난 걸 확인할 수 있습니다.


* 참고자료 출저 : http://www.nextree.co.kr/p11104/
