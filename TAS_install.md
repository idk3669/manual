# TAS 설치

## 전제조건

Ops Manager에 맞게 환경을 준비하고 BOSH Director를 설치 및 구성하는 단계를 성공적으로 완료하세요 [opsmanager 설치 링크]


## TAS 설치

**[VMware Tanzu 네트워크](https://network.pivotal.io/) 에서 제품을 다운로드하십시오.**
![image](https://user-images.githubusercontent.com/66672864/220245961-e6242aac-7c89-4691-8da4-b8671abd646f.png)
1. 설치하고자 하는 Tanzu Application Service(TAS) release 버전을 선택하십시오.
2. 다운받을 Tanzu Application Service(TAS) 파일을 선택하세요
3. 설치하고자 하는 파일의 상세 정보를 확인하십시오.
4. 설치 시 Depends On을 확인하여 의존 관계가 존재하는지 확인하십시오.

---

### Ops Manager에 VM용 TAS 추가

TAS를 구성하려면 먼저 Ops Manager 설치 대시보드에 VM용 TAS 타일을 추가해야 합니다.
<img width="1053" alt="image" src="https://user-images.githubusercontent.com/66672864/220246301-b7d4fad7-9e77-4eb8-a5aa-a98a4655e084.png">


IMPORT A PRODUCT을 클릭하여 파일을 import 시켜줍니다.
![image](https://user-images.githubusercontent.com/66672864/220246379-3fadf8e4-0619-4f6e-a887-89df707bc2ec.png)

추가된 TAS 타일을 클릭하여 설정창으로 이동합니다.
<img width="1054" alt="image" src="https://user-images.githubusercontent.com/66672864/220246627-f89619b3-f5a0-4c04-ac77-6bde2aa8a32b.png">

--- 

### AZ 및 네트워크 할당
네트워킹 창 에서 IaaS에 대한 보안 및 라우팅 서비스를 구성합니다.
<img width="1266" alt="image" src="https://user-images.githubusercontent.com/66672864/227864988-f939f67b-47df-47e9-a957-e71a415e1bbc.png">

Place singleton jobs 에서 첫 번째 AZ를 선택합니다 . Ops Manager는 이 AZ에서 단일 인스턴스로 모든 작업을 실행합니다.

Balance other jobs 에서 모든 AZ를 선택합니다 . Ops Manager는 지정한 AZ에서 작업 인스턴스를 둘 이상의 인스턴스와 균형을 맞춥니다.


### 도메인
앱 도메인과 시스템 도메인 모두에 대해 와일드카드 DNS 레코드를 구성합니다.
<img width="1261" alt="image" src="https://user-images.githubusercontent.com/66672864/227865050-63dbf112-5269-4bdc-b069-f14b038958de.png">

**시스템 도메인** 필드에 시스템 도메인의 이름을 입력합니다 . 시스템 도메인은 로드 밸런서 또는 HAProxy와 같은 VM용 TAS에 앱을 푸시할 때 대상을 정의합니다. VM용 TAS는 UAA 및 Apps Manager와 같은 시스템 구성 요소를 이 도메인 아래의 하위 도메인에 할당합니다

**앱 도메인** 필드 에 앱 도메인의 이름을 입력합니다 . 앱 도메인은 앱이 호스트 이름에 사용하는 기본 도메인입니다. VM용 TAS는 이 도메인 아래의 하위 도메인에서 각 앱을 호스팅합니다. Cloud Foundry 명령줄 인터페이스(cf CLI)를 사용하여 개별 앱에 할당된 하위 도메인을 추가하거나 삭제할 수 있습니다.


### 네트워킹
<img width="1258" alt="image" src="https://user-images.githubusercontent.com/66672864/226275415-426ad9b1-c86d-4b01-89f6-dadfbaa0a707.png">

Gorouter IPs : gorouter IP 대역을 설정합니다

SSH Proxy IPs :  대역을 설정합니다

HAProxy IPs : gorouter IP 대역을 설정합니다

TCP router IPs : gorouter IP 대역을 설정합니다

**Certificates and private keys for the Gorouter and HAProxy**

하나 이상의 인증서와 개인 키 이름 및 인증서 키 쌍을 Gorouter 및 HAProxy에 제공해야 합니다.

<img width="1021" alt="image" src="https://user-images.githubusercontent.com/66672864/227857749-df6b1c5f-96ca-4ca4-8bc9-9f12192205f4.png">


