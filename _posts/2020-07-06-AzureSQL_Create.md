---
layout : post
title : AzureSQL Create (AzureSQL 생성)
comments : true
---

![azure-sql-database.png](/assets/AzureSQL_Create/azure-sql-database.png)


https://azure.microsoft.com/ko-kr/free/

우선 AzureSQL을 만들기 위해선 Azure 체험계정이 필요합니다.

Azure는 기본적으로 구독방식(subscribe) 으로 운용이 되는데

어떤 구독 패키지이냐에 따라 가격이 천차만별 입니다.

Azure를 처음 사용하시는 분들께는 Microsoft에서 체험구독이라는 것을 주는데

이는 한달 간의 23만원 가량의 체험크레딧과 체험크레딧을 모두 소진하시거나

한달의 시간이 지나면 1년간 Linux나 Windows Server 가상머신, 블롭스토리지 등의 몇몇의 주요 서비스들을 무료로 이용하실 수 있습니다.

하지만 무료인 것도 한도란 것이 있기에 가상머신을 두 개 이상 사용하신다던지 하신다면 한도초과로 초과된 금액만큼의 요금을 지불하셔야 합니다.

자세한 사항은 밑의 링크를 참조해 주세요.

https://azure.microsoft.com/ko-kr/free/



![createAzure_01.png](/assets/AzureSQL_Create/createAzure_01.png)

Azure에 로그인하시고 Azure 포탈에 들어오셔서 위의 검색창에 AzureSQL을 검색해주세요.



![createAzure_02.png](/assets/AzureSQL_Create/createAzure_02.png)


위의 화면에서 AzureSQL 리소스 만들기를 클릭해주세요.


![createAzure_03.png](/assets/AzureSQL_Create/createAzure_03.png)

SQL배포 옵션에서는 SQL 데이터베이스 항목에서 단일 데이터베이스를 선택해주시고 만들기를 눌러줍니다.

![createAzure_04.png](/assets/AzureSQL_Create/createAzure_04.png)

다음과 같은 화면에서 리소스 그룹부터 지정해줍니다.

만일 리소스 그룹이 없으시다면 새로만들기를 클릭하셔서 새로운 리소스 그룹 이름을 지정해주시고 확인을 눌러줍니다.

![createAzure_05.png](/assets/AzureSQL_Create/createAzure_05.png)

그 다음 데이터베이스 이름을 지정해주시고 데이터 베이스 서버를 새로만들기 눌러줍니다.

![createAzure_06.png](/assets/AzureSQL_Create/createAzure_06.png)

일단 서버이름은 Azure 내에서 고유해야하므로 고유한 이름을 지정해줍니다.

그리고 관리자 로그인을 위해 필요한 아이디와 비밀번호를 적어줍니다.

Location 위치는 자신이 하고싶으신 Region(리전)을 선택하시면 됩니다.

저는 KoreaCentral(한국 중부)를 선택했습니다.



![createAzure_07.png](/assets/AzureSQL_Create/createAzure_07.png)

그리고 탄력적 풀(Elastic Pool) 사용은 아니오로 체크해주시고 컴퓨팅 스토리지 사양을 바꾸어 줍니다.

데이터 베이스 구성을 클릭해줍니다.


![createAzure_08.png](/assets/AzureSQL_Create/createAzure_08.png)


기본적으로 표준으로 체크 되어 있을텐데 표준은 공부하는 학생 입장에서

 비싼 금액이기 때문에 더욱 더 낮은 사양으로 낮추어 줍니다.

 기본항목을 클릭해주세요.


![createAzure_09.png](/assets/AzureSQL_Create/createAzure_09.png)


그러면 다음과 같이 금액이 더욱 더 낮추어 진걸 확인하실 수 있습니다.

애시당초 Azure Cloud SQL을 사용하기 위한 공부용이기에 큰 사양은 필요하지
않고

기본 옵션만으로도 원하는 어플리케이션 구축을 위하는 것에는 무리가 없으실 겁니다.

그리고 확인을 눌러줍니다.


![createAzure_10.png](/assets/AzureSQL_Create/createAzure_10.png)

다음 : 네트워킹> 버튼을 클릭해줍시다.

![createAzure_11.png](/assets/AzureSQL_Create/createAzure_11.png)

연결 방법은 퍼블릭 엔드포인트를 클릭하여 줍니다.

JDBC를 이용하기 위한 URL로써 쓰이는 엔드포인트 입니다.

Azure서비스 및 리소스가 이 서버에 액세스 할 수 있도록 허용을 아니오로
눌러줍니다.

그리고 보안설정으로 현재 클라이언트 IP주소추가에 예를 선택해줍니다.

왜냐하면 AzureSQL DB를 엔드포인트로 접근하려면 허용된 공인 아이피만

접근이 가능한데 자신의 공인아이피를 보안설정에 허용으로 추가하겠다는 말입니다.

![createAzure_12.png](/assets/AzureSQL_Create/createAzure_12.png)

그리고 다음 추가설정에서 기존 데이터 사용을 샘플을 눌러줍시다.

없음으로 하셔서 새로 하셔도 되지만 우선 지금은 AzureSQL 서버를 테스트 해보기 위함이니

샘플을 눌러주도록 합시다.

그리고 Advanced Data Security 도 나중에를 체크해줍시다.

![createAzure_13.png](/assets/AzureSQL_Create/createAzure_13.png)

그리고 최종적으로 자신이 설정했던 것들을 한번 더 검토해주시고 새로만들기를

클릭해줍니다.

![createAzure_14.png](/assets/AzureSQL_Create/createAzure_14.png)

배포 진행 중이라는 메시지가 뜹니다.

보통은 1~2분 기다리시면 되고 길면 3분까지 기다리셔야 합니다.

![createAzure_15.png](/assets/AzureSQL_Create/createAzure_15.png)

배포가 완료되면 다음과 같이 배포가 완료됨 이라는 메시지가 나타납니다.

![createAzure_16.png](/assets/AzureSQL_Create/createAzure_16.png)

그렇다면 다음과 같이 클라이언트에게 SQL요청을 받은 SQL Server와 그 안에

구축될 데이터베이스가 각각 하나씩 생성됩니다.

![createAzure_17.png](/assets/AzureSQL_Create/createAzure_17.png)

그리고 mokaimSQL에 들어가보시면(다른 이름으로 DB이름을 설정하셨다면 설정하신 이름) 좌측 메뉴에 쿼리 편집기가 보이실겁니다.

쿼리 편집기를 클릭하시면 지금과 같은 로그인 화면이 나오실텐데 아까전에

설정하셨던 SQL server의 관리자 아이디와 비밀번호를 입력하시면 됩니다.

![createAzure_18.png](/assets/AzureSQL_Create/createAzure_18.png)


그리고 쿼리에 아래와 같은 명령어를 입력해봅시다.

아까 기존 데이터 사용에서 테스트용으로 미리 체크해두었던

샘플DB에서 셀렉트 시켜오는 쿼리입니다.


<script src="https://gist.github.com/mokaim/cad3965d781ae68da270c2b3f6d23599.js"></script>




![createAzure_19.png](/assets/AzureSQL_Create/createAzure_19.png)


성공적으로 쿼리가 조회되는 것을 확인하실 수 있으시겠습니다.

자세한 사항은 Microsoft 공식 메뉴얼을 참조하시면 되겠습니다.


출저 : https://docs.microsoft.com/ko-kr/azure/azure-sql/database/single-database-create-quickstart?tabs=azure-portal
