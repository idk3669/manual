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
