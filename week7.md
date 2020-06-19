

## Core Cloud Services - Azure 데이터 스토리지 옵션

이 장에서는 Azure 데이터 스토리지 및 온프레미스 스토리지의 이점에 대해서 각각 알아보자!

---

## 데이터를 저장할 때 Azure를 사용해서 뭐가 좋을까?

예를들어 온라인 학습포털의 스토리지 문제를 해결하기위해 클라우드에 데이터를 저장하는 것을 고려하고 있다고 하자. 보안, 백업 및 재해복구에 대한 우려 등등.. 걱정이 많다. 무엇보다 클라우드에서 호스트된 데이터를 관리하는 방법이 어려워질 것이 걱정이다.

Azure 데이터 스토리지 옵션은 클라우드 기반으로 보호되는 확장 가능한 기능이다. 이 기능을 통해 클라우드 스토리지의 핵심 과제를 해결하고 안정성과 내구성이 좋은 스토리지 솔루션을 제공하자!

### 클라우드에 데이터를 저장하는 이유

데이터 형식에 상관없이 내 데이터에 엑세스하고, 업데이트하고, 공유할 수 있기를 원한다. 클라우드 저장소 공급자는 표준 데이터 엑세스 방법을 사용하는데, 포인트에서 낭비를 하거나 통신에 업계 표준을 사용하여 데이터를 넓은 범위의 응용프로그램 종류 및 플랫폼에 사용할 수 있도록 돕는다. 그리고 Azure의 경우 데이터 저장소 작업을 간소화하는 API와 함께 개발자 패키지 및 라이브러리를 사용하면 더 쉽게 통신할 수 있게 한다. 또한 다양한 데이터 형식에 대해 여러 클라우드 저장소 서비스를 제공한다.

### 데이터를 저장하는데 Azure를 사용하는 이점

-   자동화된 백업 및 복구
-   전세계에서 복제 : 데이터를 복사해 예약된 유지관리 또는 하드웨어 오류와 같은 계획되거나 계획되지 않은 이벤트에 대비해 데이터를 보호
-   데이터 분석 지원
-   암호화 기능
-   다양한 데이터 형식
-   가상 디스크의 데이터 스토리지
-   스토리지 계층

#### 데이터 형식

Azure Storage에 저장할 수 있는 기본적인 데이터 형식은 세가지가 있다.

1.  **정형 데이터 (Structured data)**
    -   스키마를 준수하는 데이터
    -   모든 데이터에 동일한 필드 또는 속성이 있다. 행 및 열이 있는 데이터베이스 테이블에 저장된다.
    -   정형 데이터는 Key를 사용하여 테이블의 한 행을 다른 테이블의 또 다른 행에 있는 데이터와 연결하는 방법을 나타낸다.
    -   데이터의 스키마가 데이터의 테이블, 테이블의 필드, 둘 사이의 명확한 관계를 정의하므로 정형 데이터는 관계형 데이터라고도 한다. 
    -   입력하고 쿼리하고 분석하기 쉽다.
    -   모든 데이터가 동일한 형식을 따른다.
2.  **반정형 데이터(Semi-structured data)**
    -   테이블, 형, 열에 잘 맞지 않는 데이터
    -   데이터 계층 구조를 구성하고 제긍하는 태그 또는 키 사용
    -   _비관계형_ 또는 _NoSQL_ 데이터라고도 한다.
3.  **비정형 데이터(Unstructrued data)**
    -   지정된 구조가 없는 데이터를 포괄한다
    -   구조가 없다는 것은 포함될 수 있는 데이터 종류에 대한 제한이 없다는 것을 의미한다.
    -   예를들어 하나의 Blob에 PDF문서, JPG 이미지, JSON 파일, 동영상 콘텐츠 등이 포함될 수 있다.
    -   기업에서 새 데이터 원본을 활용하려고 함에 따라 비정형 데이터가 보급되고 있다.

---

## Azure 데이터 스토리지가 비즈니스 스토리지 요구사항을 충족하는 방법

Azure 데이터 스토리지의 이점을 살펴보고 학습 포털을 저장하는 데 가장 적합한 옵션을 제공하는 것을 이해해보자.

Azure는 특정 유형의 데이터 스토리지 요구 사항을 충족하는 몇 가지 옵션을 제공한다.

### 1\. Azure SQL Database

Azure SQL Database는 안정적인 최신 Microsoft SQL Server 데이터베이스 엔진 버전을 기반으로 하는 관계형 DaaS(Database as a Service)다. SQL Database는 안정적이고 고성능을 제공하는 완전 관리형 데이터베이스다. 인프라를 관리할 필요 없이 선택한 프로그래밍 언어로 데이터 기반 어플리케이션 및 웹사이트를 빌드하는데 사용할 수 있다.

Azure Database Migration Service를 사용하면 최소한의 다운타임으로 기존의 SQL Server 데이터베이스를 마이그레이션 할 수 있다. 이 서비스는 Microsoft Data Migration Assistant를 사용하여 마이그레이션을 수행하기 전에 필요한 변경 사항을 설명하는 권장 사항을 제공하는 평가 보고서를 생성한다. 필요한 수정을 평가하고 수행했으면 마이그레이션 프로세스를 시작할 수 있다. 

아래 그림은 Azure SQL Database에 저장되어 있는 온라인 학습 포털 시나리오 데이터 형식을 보여준다.

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FljjBD%2FbtqEqsXVzex%2FDepjnxeyyb4OfZH4ahh2pK%2Fimg.png)

### 2\. Azure Cosmos DB

Azure Cosmos DB는 글로벌 분산형 데이터베이스 서비스다. 지속적으로 변경되는 데이터를 지원하기 위해 응답성이 뛰어난 Always On 어플리케이션을 빌드할 수 있는 스키마가 없는 데이터를 지원한다. 이 기능을 사용하여 전 세계 사용자가 업데이트하고 유지관리하는 데이터를 저장할 수 있다.

아래는 전세계 사람들이 엑세스하는 데이터를 저장하는데 사용되는 Azure Cosmos DB 를 보여준다.

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FnUZMO%2FbtqEpJlBotS%2FF9TqVJQkJyfXjLHRTYHUzK%2Fimg.png)

### 3\. Azure Blob Stroage

Azure Blob Storage는 비정형이므로 포함될 수 있는 데이터 종류에 대한 제한이 없다. Blob은 확장성이 뛰어나며, 앱은 디스크의 파일을 사용하는 것과 거의 동일한 방식으로 Blob을 사용한다. Blob Storage는 수천 개의 동시 업로드, 대용량 비디오 데이터, 끊임없이 증가하는 로그 파일을 관리할 수 있으며, 어디서나 인터넷을 통해 연결할 수 있다.

Blob은 일반적인 파일 형식으로 제한되지 않는다. 즉, 하나의 Blob에 과학 기기에서 스트리밍된 몇 기가바이트의 이진 데이터, 다른 어플리케이션용 암호화된 메세지 또는 개발중인 앱에 대한 사용자 지정 형식의 데이터가 포함될 수 있다.

Azure Blob Storage를 사용하면 전 세계 어디에서나 대용량의 비디오 또는 오디오파일을 사용자의 브라우저로 직접 스트리밍할 수 있다. Blob Storage를 사용하여 백업, 재해복구 및 보관용 데이터를 저장하기도 한다. 최대 8TB의 가상 머신용 데이터를 저장할 수 있다.

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FdxlBLM%2FbtqEoAbNpQh%2FaiaFJK8XvUIIK8mzS3T2E0%2Fimg.png)


### 4\. Azure Data Lake Storage

Data Lake 기능을 사용하면 데이터 사용량을 분석하고 보고서를 준비할 수 있다. Data Lake는 구조적 데이터화 비정형 데이터가 모두 저장되는 대형 레포지토리다.

Azure Data Lake Storage에는 개체 스토리지의 확장성 및 비용 혜택이 빅데이터 파일 시스템 기능의 안정성 및 성능과 결합되어있다. 

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FcAlX5Y%2FbtqEo8zgkak%2FyWfkpqrPgPVQrWCLNy6zJk%2Fimg.png)

### 5\. Azure Files

Azure Files는 산업 표준 SMB(서버 메세지 블록) 프로토콜을 통해 액세스할 수 있는 클라우드에서 완전 관리형 파일 공유를 제공한다. Azure File 공유는 Windows, Linux 및 macOS의 클라우드 또는 온프레미스 배포를 통해 동시에 탑재될 수 있다. Azure 가상머신이나 클라우드 서비스에서 실행되는 어플리케이션은 데스크톱 어플리케이션이 일반적인 SMB 공유를 탑재하는 것처럼 File Storage 공유를 탑재하여 파일 데이터에 엑세스할 수 있다. 제한 없는 수의 Azure 가상 머신 또는 역할이 파일 스토리지 공유를 동시에 탑재하고 엑세스할 수 있다. 일반적인 사용 시나리오로는 전 세계 어디서나 파일을 공유하고, 진단 데이터 또는 어플리케이션 데이터를 공유하는 경우가 있다. 

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FbwPdmb%2FbtqEq8Sw61V%2FSRbIEwpbqDtlld5OHFM9l1%2Fimg.png)

### 6\. Azure Queue

Azure Queue Storage는 전 세계 어디서나 엑세스할 수 있는 많은 수의 메세지를 저장하기 위한 서비스다.

Azure Queue Storage를 사용하여 유연한 어플리케이션을 구축하고 기능을 분리하여 대용량 워크로드 전반에서 내구성을 향상시킬 수 있다. 어플리케이션 구성요소가 분리되면 독립적으로 확장이 가능하다. Queue Storage는 클라우드, 데스크톱, 온프레미스 또는 모바일 디바이스에서 실행되는 어플리케이션 구성요소 간의 통신을 위해 비동기식 메시지 대기열 기능을 제공한다.

일반적으로 하나 이상의 송신기 구성 요소와 하나 이상의 수신기 구성 요소가 있다. 송신기 구성 요소는 큐에 메세지를 추가하는 반면 수신기 구성 요소는 큐 앞에서 처리할 메세지를 검색한다.

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FcpZQ7A%2FbtqEo8spk7g%2F2EyLx3RnEXXzapXInre7Qk%2Fimg.png)

큐 스토리지를 통해 아래를 수행할 수 있다.

-   작업 백로그를 만들고 다른 Azure 웹서버 간에 메세지를 전달한다.
-   여러 웹 서버/인프라 간에 로드를 배포하고 트래픽 증가를 관리한다.
-   여러 사용자가 동시에 데이터에 엑세스할 때 구성 요소 오류에 대한 복원력을 빌드한다.

### 7\. Disk Storage

Disk Storage는 가상머신, 어플리케이션 및 기타 서비스가 온프레미스 시나리오와 마찬가지로 필요에 따라 엑세스하여 사용할 수 있는 디스크를 제공한다. Disk Storage는 데이터를 연결된 가상 하드 디스크에서 영구적으로 저장 및 엑세스할 수 있게 해준다. 디스크는 Azure에서 관리하거나 관리하지 않을 수 있으므로 사용자가 관리하고 구성할 수 있다. Disk Storage를 사용하는 일반적인 시나리오로는 데이터를 읽고 영구 디스크에 쓰는 어플리케이션을 리프트 앤 시피트 하는 경우 또는 디스크가 연결된 가상 머신 외부에서 엑세스할 필요가 없는 데이터를 저장하는 경우가 있다.

디스크는 SSD(Solid-State Drive)부터 기존의 회전식 하드 디스크 드라이브(HDD)까지 다양한 크기의 성능 수준으로 제공된다.

VM을 사용할 때 덜 중요한 워크로드에는 표준 SSD 및 HDD 디스크를 사용하고 중요 업무용 프로덕션 어플리케이션에는 프리미엄 SSD 디스크를 사용할 수 있다. 

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FpdQKZ%2FbtqEqswWybj%2FmJdQfzhqA3r81vQzFDyQn1%2Fimg.png)

### 8\. 스토리지 계층

Azure는 Blob 개체 스토리지에 다음 세가지 스토리지 계층을 제공한다.

1.  **핫 스토리지 계층** : 자주 엑세스하는 데이터를 저장하는 데 최적화되어 있다.
2.  **쿨 스토리지 계층** : 드물게 엑세스되고 최소 30일 동안 저장되는 데이터에 최적화되어 있다.
3.  **보관 스토리지 계층** : 유연한 대기 시간을 요구사항으로 최소 180일 동안 거의 액세스 및 저장되지 않은 데이터에 최적화 되어 있다.

### 9\. 암호화 및 복제

Azure는 암호화 및 복제 기능을 통해 보안 및 고가용성 데이터에 제공한다.

#### 스토리지 서비스 암호화

리소스에서 사용할 수 있는 암호화 유형은 아래와 같다.

1.  미사용 데이터에 대한 **Azure SSE(스토리지 서비스 암호화)**를 사용하면 조직의 보안 및 규정 준수를 충족하도록 데이터를 보호할 수 있다. 데이터를 저장하기 전에 암호화하고 데이터를 검색하기 전에 암호를 해독한다. 암호화 및 암호 해독은 사용자에게 투명하게 이루어진다.
2.  **클라이언트 쪽 암호화**에서는 클라이언트 라이브러리에 의해 데이터가 이미 암호화 되어있다. Azure는 암호화된 상태로 미사용 데이터를 저장한 다음, 검색중에 암호를 해독한다.

#### 스토리지 가용성 복제

복제 유형은 스토리지 계정을 만들 때 설정된다. 복제 기능은 데이터가 내구성이 있으며 항상 사용할 수 있는지 확인한다. Azure는 화재나 홍수 같은 자연재해 및 기타 지역 재해로부터 데이터를 보호하기 위한 지역 및 지리적 복제를 제공한다.

---

## Azure 데이터 스토리지와 온-프레미스 스토리지 비교

다음 표에서는 온-프레미스 스토리지와 Azure 데이터 스토리지 간의 차이점을 보여 줍니다.

<table style="border-collapse: collapse; width: 100%; height: 254px;" border="1" data-ke-style="style1"><tbody><tr><td style="text-align: center;"><b>필요</b></td><td style="text-align: center;"><b>온프레미스</b></td><td style="text-align: center;"><b>Azure 데이터 스토리지</b></td></tr><tr style="height: 17px;"><td style="height: 17px;">규정 준수 및 보안</td><td style="height: 17px;">개인 정보 보호 및 보안에 필요한 전용 서버</td><td style="height: 17px;">클라이언트 쪽 암호화 및 미사용 암호화</td></tr><tr style="height: 35px;"><td style="height: 35px;">정형 및 비정형 데이터 저장</td><td style="height: 35px;">전용 서버를 사용하는 추가 IT 리소스 필요</td><td style="height: 35px;">Azure Data Lake 및 포털은 모든 형식의 데이터를 분석하고 관리합니다.</td></tr><tr style="height: 17px;"><td style="height: 17px;">복제 및 고가용성</td><td style="height: 17px;">추가 리소스, 라이선싱 및 서버 필요</td><td style="height: 17px;">사용 가능한 기본 제공 복제 및 중복 기능</td></tr><tr style="height: 35px;"><td style="height: 35px;">애플리케이션 공유와 공유 리소스에 대한 액세스</td><td style="height: 35px;">파일 공유에는 추가 관리 리소스가 필요합니다.</td><td style="height: 35px;">추가 라이선스 없이 사용 가능한 파일 공유 옵션</td></tr><tr style="height: 35px;"><td style="height: 35px;">관계형 데이터 스토리지</td><td style="height: 35px;">데이터베이스 관리자 역할이 있는 데이터베이스 서버가 필요</td><td style="height: 35px;">Database-as-a-Service 옵션 제공</td></tr><tr style="height: 35px;"><td style="height: 35px;">분산 스토리지 및 데이터 액세스</td><td style="height: 35px;">비용이 많이 드는 스토리지, 네트워킹, 컴퓨팅 리소스 필요</td><td style="height: 35px;">Azure Cosmos DB는 분산 액세스를 제공합니다.</td></tr><tr style="height: 35px;"><td style="height: 35px;">메시지 및 부하 분산</td><td style="height: 35px;">하드웨어 중복은 예산 및 리소스에 영향을 줍니다.</td><td style="height: 35px;">Azure Queue는 효과적인 부하 분산을 제공합니다.</td></tr><tr style="height: 35px;"><td style="height: 35px;">계층화된 스토리지</td><td style="height: 35px;">계층화된 스토리지를 관리하려면 기술 및 노동 기능이 필요합니다.</td><td style="height: 35px;">Azure는 계층화된 자동 데이터 스토리지를 제공합니다.</td></tr></tbody></table>

#### 1\. 비용 효과

온프레미스 스토리지 솔루션에는 구매, 설치, 구성, 유지 관리해야하는 전용 하드웨어가 필요하다. 상당한 선행비용이 필요하며, 새 하드웨어에 대한 투자가 필요할 수 있다. 하드웨어가 최대 수요를 처리할 수 있어야 한다. 

Azure 데이터 스토리지는 선행 자본이 아닌 운영 비용으로 종량제 가격 책정 모델이 적용된다. 확장성이 뛰어나기 때문에 요구 사항에 따라 확장하거나 스케일 아웃 했다가 수요가 줄어들면 다시 축소할 수 있다.

#### 2\. 안정성

온프레미스 스토리지에는 데이터 백업, 부하분산 및 재해복구 전략이 필요하다. 이 요구사항은 하드웨어 및 IT 리소스 모두에 막대한 투자가 요구되는 전용 서버가 필요하기 때문에 어렵고 비용이 많이 든다.

Azure 데이터 스토리지는 데이터 백업, 부하 분산, 재해 복구 및 데이터 복제를 서비스 형태로 제공하기 때문에 데이터 안정성과 높은 가용성을 보장한다.

#### 3\. 스토리지 유형

파일 및 데이터베이스 스토리지와 같은 솔루션에 여러가지 스토리지 유형이 필요한 경우가 있다. 온프레미스 방식에는 스토리지 유형마다 다수의 서버와 관리 도구가 필요한 경우가 많다.

Azure 데이터 스토리지에는 분산 엑세스 및 계층형 스토리지를 비롯한 다양한 스토리지 옵션이 제공되는데, 솔루션의 각 부분에 대해 최상의 스토리지 옵션을 제공하는 스토리지 기술의 조합을 통합할 수 있다.

#### 4\. 민첩성

요구 사항 및 기술은 변화한다. 온프레미스 배포의 경우 이러한 변화가 생기면 새로운 서버와 인프라를 프로비저닝하고 배포해야하므로 시간과 비용이 많이 든다.

Azure 데이터 스토리지는 몇분안에 새로운 서비스를 만들 수 있는 유연성을 제공한다. 이러한 유연성 덕분에 하드웨어에 상당한 투자를 하지 않고도 스토리지 백엔드를 신속하게 변경할 수 있다.

출처 : <https://docs.microsoft.com/ko-kr/learn/modules/intro-to-data-in-azure/>