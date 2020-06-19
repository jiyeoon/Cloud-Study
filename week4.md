
CLI 환경에서도 Azure에 쉽게 접근할 수 있다.

### Azure Cloud Shell이란?

Azure Cloud Shell은 Azure 리소스를 관리하고 개발하기 위한 브라우저 기반 환경이다. Cloud shell을 그냥 클라우드에서 실행되는 대화형 콘솔임.

(마이크로소프트답게) Cloud Shell은 선택할 수 있는 환경은 Bash와 Power Shell이 있다. 두 환경 모두 Azure CLI와 Azure Powershell에 대한 엑세스를 제공한다.

배포한 웹 사이트가 여러 개 있는데 Azure Portal을 사용하여 각각 App Service에 개별적으로 엑세스하지 않고 각각의 웹사이트를 시작 또는 중지하려고 한다고 가정해보자. 이 작업은 cloud shell과 azure CLI를 이용해서 스크립트로 변환할 수 있는 쉬운 작업이다.

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FbdScBd%2FbtqElEMvcox%2FCJveJXkhkjL9Cpb1XIusyK%2Fimg.png)

저걸 누르면 커맨드창이 나오면서 명령어를 입력할 수 있다.

### Azure CLI 사용해보기!

#### 1\. 현재 구독 정책 확인

먼저 올바른 Azure 구독을 사용하고 있는지 확인해보자.

```bash
az account list --output table  
```

이 명령은 json 문자열을 반환한다.

#### 2\. 리소스 그룹 확인하기

```bash
az group list --output table  
```

#### 3\. 해당 리소스 그룹에서 사용하고 있는 모든 리소스를 표시해보자.

'resource-type'라는 옵션을 주면서 웹사이트와 관련있는 리소스 정보만 포함하도록 필터링했다.

```bash
az resource list  
\--resource-group learn-43f1d90e-7801-4c68-8817-f4ef777c12f2  
\--resource-type Microsoft.Web/sites  
```

아래는 출력 예시다.

```bash
{  
"id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx/resourceGroups/learn-43f1d90e-7801-4c68-8817-f4ef777c12f2/providers/Microsoft.Web/sites/BlogFor",  
"identity": null,  
"kind": "app",  
"location": "centralus",  
"managedBy": null,  
"name": "MyWebApp",  
"plan": null,  
"properties": null,  
"resourceGroup": "learn-43f1d90e-7801-4c68-8817-f4ef777c12f2",  
"sku": null,  
"tags": null,  
"type": "Microsoft.Web/sites"  
}  
```

'name'의 값을 복사하자.

#### 4\. 실행중인 웹 어플리케이션 중지하기

'az webapp stop' 명령을 사용해 App Service에서 실행중인 웹어플리케이션을 중지해보자.  
을 복사한 웹앱의 이름으로 바꾸어 중지하자.

```bash
az webapp stop  
\--resource-group learn-43f1d90e-7801-4c68-8817-f4ef777c12f2  
\--name  
```