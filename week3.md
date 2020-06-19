
App Service에서 호스트되는 웹사이트를 배포해보자!

#### App Service란?

Azure App Service란 인프라를 관리하지 않고도 다양한 유형의 웹기반 솔루션을 빌드 및 호스트할 수 있도록 지원하는 http 기반 서비스다. 예를들어, 몇가지 지원되는 프로그래밍 언어로 웹앱, 모바일 백엔드 및 RESTful API를 호스트할 수 있다. .Net, .NET core, Java, Ruby, Node.js, PHP, Python 등등.. 거의 다 되는 듯?

앱서비스를 사용하면 다양한 확장 프로그램을 짧은 시간 안에 만들 수 있다. 이때 Microsoft Azure Marketplace에서 사전 정의된 어플리케이션을 사용해야한다.

#### Microsoft Azure Marketplace란?

Microsoft Azure Marketplace는 Azure에서 실행되도록 인증받고 최적화된 어플리케이션을 호스트하는 온라인 스토어다. (약간 앱스토어같은 느낌?) AI, 기계학습부터 웹어플리케이션까지 다양한 유형의 어플리케이션을 찾을 수 있다. 스토어에서의 배포는 마법사 스타일의 사용자 인터페이스를 사용하여 Azure Portal을 통해 진행된다. 이 사용자 인터페이스를 사용하면 여러 솔루션을 손쉽게 평가할 수 있다.

이번 실습에서는 WordPress 를 사용해 웹사이트를 만들어보자!

---

### 1\. Azure에서 리소스 만들기

일반적으로 가장 먼저 할 일은 만들어야할 모든 항목을 보관할 리소스 그룹을 만드는 것이다. 리소스 그룹을 사용하면 솔루션을 구성하는 모든 서비스, 디스크, 네트워크 인터페이스 및 요소를 하나의 단위로 관리할 수 있다. 솔루션의 리소스 그룹은 Azure Portal을 사용하여 만들고 관리할 수 있다. (Azure CLI를 통해서도 가능)

이번 실습에서는 Azure 샌드박스 환경에서 미리 만들어진 리소스 그룹인 **learn-6d70a5ff-5cfd-4464-abc5-b02c4b735b02**을 사용할 것이므로 이 단계를 수행할 필요가 없다. (나중엔 따로 만들어야한다는 소리겠지?!)

### 2\. 위치 선택

무료 샌드박스를 사용하면 Azure 글로벌 지역의 일부 하위 지역에 리소스를 만들 수 있다. 리소스를 만들 때 다음 목록에서 지역을 선택한다.

-   westus2
-   southcentralus
-   centralus
-   eastus
-   westeurope
-   southeastasia
-   japaneast
-   brazilsouth
-   australiasoutheast
-   centralindia

(대충 보면 이름만 봐도 어디 지역인지 감이 온다!)

### 3\. Wordpress 웹사이트 만들기

먼저 샌드박스를 활성화한다. (이 부분은.. 귀찮으니 링크 [https://docs.microsoft.com/ko-kr/learn/modules/welcome-to-azure/4-exercise-create-website](https://docs.microsoft.com/ko-kr/learn/modules/welcome-to-azure/4-exercise-create-website))

2\. 샌드박스를 활성화한 계정과 동일한 계정을 사용하여 Azure Portal에 로그인한다.

3\. 메뉴 버튼을 눌러 '리소스 만들기' 선택~ 그러면 Azure Marketplace가 바로 뜬다.

![img1](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FbkE1hm%2FbtqEjPGFq1r%2FP4MuUuFAAd45kYmme4eWKK%2Fimg.png)

4\. 여기서 'WordPress' 를 검색한다. WordPress 클릭. (on Linux말고1!)

![img2](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fk40uI%2FbtqEiL58btB%2FHRSC8fXF6mTAueUDbXkXVk%2Fimg.png)

5\. '만들기' 버튼 클릭!!

![img3](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FyVLLh%2FbtqEil7DEZN%2F38sLEy6dd8PpWCaELOm8Vk%2Fimg.png)

6\. 뭐 이것저것 채워야하는게 많이 있는데.. 이때

-   앱 이름 : 고유한 앱 이름을 입력. 난 대충 practice 어쩌구 이런 식으로 넣었다.
-   구독 : 컨시어지 구독으로 선택
-   리소스 그룹 : 기존 항목 사용 클릭 -> 드롭다운 목록에서 **learn-6d70a5ff-5cfd-4464-abc\*\***5-b02c4b735b02\*\*리소스 그룹을 선택
-   데이터베이스 공급자 : MySQL in APP 선택
-   Application Insights : 걍 그대로 둠

![img4](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FxbAVV%2FbtqEils2nli%2FsU6HpSyBLGq0F5NRKjVe40%2Fimg.png)

7\. 'App Service 계획' 클릭 후 '새로 만들기' 선택

![img5](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fb5hUjJ%2FbtqElkm6n6n%2FEPp1roc6vAKZXkQ2TdQ3Pk%2Fimg.png)

10\. '새 App Service 계획' 패널에서 새 서비스 플랜의 이름을 입력한다. (아무거나 괜찮)

11\. 위치는 일반적으로 고객에게 가장 가까운 지역을 선택하는게 일반적!

12\. 가격 책정 계층을 선택해 다양한 유형의 서비스 플랜에 대한 성능 및 기능 옵션 확

![img6](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FUajVX%2FbtqEmoPSOz1%2F90baifTPsOCN0cv8REJwzk%2Fimg.png)

13\. '사양 선택기'를 이용해 어플리케이션에 대한 새 가격 책정 계층 선택

![img7](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2F4Fd5G%2FbtqEnHnbCA4%2Fgw5K2dTAINKKvimH38sPm0%2Fimg.png)

14\. '새 App Service 계획' 패널에서 확인을 선택해 새 플랜을 만들고 패널을 닫는다

15\. 마지막으로 '만들기' 단추 선택해 새 사이트 배포 시작

### 웹사이트가 실행 중인지 확인

위의 내용을 차례차례 했으면 생성이 된 것이다! 배포 진행 상황은 언제든지 확인할 수 있다.

1\. 포털 맨 위에 있는 알림 아이콘 선택. 

![img8](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FeJpNUy%2FbtqEliXbewd%2FyI1M0nAUksiRl74Zyx1Xy1%2Fimg.png)

2\. '배포 진행중'을 선택하여 모든 리소스에 대한 세부 정보를 확인한다. 리소스가 어떻게 나열되는지 확인하고 배포의 각 구성 요소가 완료되면 녹색 확인 표시로 상태가 변경되는 것을 볼 수 있다.

![img9](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FdOVM8b%2FbtqEmvnGoqf%2FbkdauXTkzSkud23AX1gAcK%2Fimg.png)

![img10](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FpzV15%2FbtqEnI0ILYc%2FHJTQ1KM5oOygXVNLUuP2J0%2Fimg.png)

3\. 배포 상태 메세지가 '배포가 완료됨'으로 바뀌면 성공! '리소스로 이동' 클릭해서 App service 개요로 이동한다.

![img11](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fbf4h0N%2FbtqEk1VzLXu%2F8QFzBsxMpTZKySooUBHbRk%2Fimg.png)

4\. 개요 섹션에서 URL을 찾는다. 들어가보면 wordpress 사이트로 들어가진다 (오예~)

![img12](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FBETKu%2FbtqEnHgqXyu%2FudsMDUOEU5voGMcLsQTrK1%2Fimg.png)
![img13](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FmbB0M%2FbtqEniBcfuG%2FBQXzwZOAnaTA5PbEOUdEf0%2Fimg.png)

### App Service 구성

이번에는 어플리케이션에 대해 노출된 추가 정보를 확인하고 웹사이트를 구성하는데 사용할 수 있는 몇 가지 옵션을 살펴보자.

1\. 왼쪽 탐색 메뉴에서 '대시보드'를 선택해서 구독에 있는 모든 리소스 목록에 액세스한다. 탐색 선택 항목을 표시하기 위해 메뉴 아이콘을 클릭해야할 수도 있다.

![img14](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fcdd37B%2FbtqEmpONCxF%2F3jylRt3bp6u6D8NCWIi4K0%2Fimg.png)

2\. 이전에 선택한 이름의 'App Service'를 선택

![img15](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FbuJv63%2FbtqEmKkDg5t%2FkgawBQySQK0Sjwbyb41L80%2Fimg.png)

3\. 기본적으로 앱서비스의 개요가 표시된다. 

개요 보기에서 아래로 스크롤하여 새로 만든 웹사이트의 그래프를 확인할 수 있다. 그래프는 웹사이트에서 수신된 요청의 개수, 수신/송신된 데이터의 양, 사이트에서 발생한 오류의 개수에 관한 통계 등을 제공한다.

![img16](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FrF0j7%2FbtqEnHHvdfD%2Fj5SyQlIvT3CKAmZSxhc2G1%2Fimg.png)

> 확장하고싶어요

배포한 웹사이트를 많은 사용자가 이용하는 경우 우리는 확장을 해야한다. 확장이란 성능을 높이기 위해 네트워크 대역폭, 메모리, 스토리지 또는 컴퓨팅 성능을 추가하는 것을 의미한다. '수직확장' 및 '수평확장'이란 용어는 이전 포스팅에서 참고! 

[2020/05/12 - \[Computer Engineering\] - 컴퓨터의 성능을 높이는 방법 - 스케일업(scale up)과 스케일 아웃(scale out)](https://butter-shower.tistory.com/109)


#### App Service 스케일 업

1\. App Service의 설정 구성 섹션에서 '스케일업 (App Service 계획)' 을 선택한다. 

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FOVKB7%2FbtqEmqfTu0h%2F9YLMiKiUQNeXQulQ1A1fw1%2Fimg.png)

2\. 구성 창에 선택할 수 있는 세 개의 워크로드 범주가 있는 것을 확인할 수 있는데, 세개의 범주를 바탕으로 우리가 실행할 워크로드의 유형을 쉽게 정할 수 있다.

<table style="border-collapse: collapse; width: 100%; height: 104px;" border="1"><tbody><tr style="height: 17px;"><td style="width: 16.2791%; height: 17px;">범주</td><td style="width: 83.7209%; height: 17px;">설명</td></tr><tr style="height: 35px;"><td style="width: 16.2791%; height: 35px;">개발/테스트</td><td style="width: 83.7209%; height: 35px;">보다 덜 까다로운 워크로드에 적합. 이 범주는 주로 공유 인프라를 제공하는데 주력한다. 이 범주에서는 App Service 어플리케이션에서 사용 가능한 추가 기능이 제공된다. 일례로 사용자 지정 도메인/SSL 및 수동 확장을 들 수 있다.</td></tr><tr style="height: 35px;"><td style="width: 16.2791%; height: 35px;">프로덕션</td><td style="width: 83.7209%; height: 35px;">더 까다로운 워크로드에 적합하다. 이 범주에서는 스테이징 슬롯, 일일 백업, 트래픽 관리자와 같은 추가 기능도 볼 수 있다.</td></tr><tr style="height: 17px;"><td style="width: 16.2791%; height: 17px;">격리</td><td style="width: 83.7209%; height: 17px;">고급 네트워킹 및 미세 소정 확장이 필요한 워크로드에 적합하다.</td></tr></tbody></table>

위에서 선택한 F1 계층의 구성에서 나가지만, 어플리케이션의 로드에 변경 사항이 있는 경우 이 창에서 App Service의 크기를 조정할 수 있다.

출처 : <https://docs.microsoft.com/ko-kr/learn/modules/welcome-to-azure/4-exercise-create-website](https://docs.microsoft.com/ko-kr/learn/modules/welcome-to-azure/4-exercise-create-website>