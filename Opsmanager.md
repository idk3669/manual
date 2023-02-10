# Opsmanager



### 개념

---

opsmanager란 tile형태의 제품을 확장하고 관리하는 데 도움이 되는 소프트웨어 도구입니다.
Tanzu Application Service for VMs의 설정을 UI 화면으로 편리하게 조작가능합니다.
또한 Opsmanager는 기본적으로 VM들을 제어하는 BOSH Director 타일과 함께 배포됩니다.
BOSH Director는 AWS, Azure, GCP, vSphere등 다영한 IaaS 환경에서 동작 할 수 있습니다.

Opsmanager에 두가지 유형으로 된 tile을 설치할 수 있습니다.

* Runtime Tiles : VM기반 런타임을 설치할 수 있습니다. 이 런타임은 애플리케이션 및 기타 프로세스를 동적으로 실행하여 애플리케이션 라이프사이클 전반에 걸쳐
  수요의 균형을 맞출 수 있습니다. 운영 관리자를 통해 관리되는 런타임을 VMware Tanzu Application Service for VMs를 사용합니다.

* Service Tiles : 런타임 환경 뿐만아니라 다양한 서비스를 설치할 수 있습니다. Opsmanager를 통해 관리되는 서비스는 Gemfire, RabbitMQ, SCS, SCG가 있습니다.
  설치할 수 있는 타일에 대한 자세한 내용은 VMware Tanzu Network를 참조할 수 있습니다. https://network.pivotal.io/



Opsmanager는 운영자가 관리하는 영역입니다. 운영자는 런타임 및 서비스 타일의 설치 및 유지 관리를 담당합니다.

- 운영자의 책임 영역은 아래과 같습니다.
  
  - Opsmanager 기능 구성
  
  - opsmanager를 외부 시스템과 통합
  
  - opsmanager및 설치된 제품 업데이트
  
  - opsmanager 상태 및 성능 모니터링
  
  - 상태 또는 성능 문제를 해결하기 위해 OpsManager 리소스 및 옵션 조정
  
  - Opsmanager 문제 진단 및 문제 해결
  
  - VM 사용자, 리소스 및 인프라용 TAS 관리
  
  - 소프트웨어 서비스 설치
  
  - Opsmanager 사용자 및 클라이언트 계정 생성 및 관리



다음은 변경 사항, 기능 추가/삭제, 버그 개선 등 변경 되는 업데이트(Releae note) 사항 링크입니다. (https://docs.pivotal.io/ops-manager/3-0/release-notes.html)



---

### 설치 방법

-  캡쳐 + 작성 예정
  
  

---

### 

### 업그레이드 방법

- 

ㄹ

---

### 사용 방법 UI

이 단계에서는 OpsManager 인터페이스의 주요 기능에 대해 설명합니다.

##### 메인페이지

* 대시보드는 런타임 tile과 서비스 tile을 관리하기 위한 OpsManager 인터페이스입니다.
  
  
  
  
  a. **IMPORT A PRODUCT** : OpsManager에 새 제품을 추가하려면 이 버튼을 클릭합니다. VMware Tanzu Network에서 OpsManager 호환 제품 파일을 가져올 수 있습니다.
  1. Tanzu Network에서 설치하고자 하는 제품을 다운로드 하십시오.
  2. OpsManager 대시보드로 이동하여 로그인합니다.
  3. Import a Product를 클릭합니다. 
  4. .pivotal 파일을 클릭합니다.
  5. 제품 목록의 + 아이콘을 클릭하여 OpsManager 대시보드에 제품 타일을 추가합니다.
  6. OpsManager 대시보드에 제품 타일이 나타납니다. 제품에 구성이 필요한 경우 타일 하단의 막대가 주황색으로 나타납니다.
  7. 제품 구성이 끝나게 되면 타일 하단의 막대가 초록색으로 나타나게 됩니다.

        

        b. **tile 삭제** 
            1. 대시보드에서 제품 타일에서 휴지통 아이콘을 클릭하여 해당 제품을 제거합니다.(BOSH Director tile은 삭제할 수 없습니다.)
            2. Review Pending Changes를 클릭합니다. 그리고 삭제하고자 하는 tile을 선택 후 Apply Chanage를 클릭합니다.
            3. tile을 삭제하면 tile이 대시보드 메인 화면에서 제거됩니다. 
            4. 하지만 Available Products에 목록으로 존재하게 됩니다.

        

        c. **Delete All Unused Products** : 설치 가능한 tile 리스트에서 모든 제품을 삭제할 수 있습니다.



        d. **Installation Dashboard** : 다른 페이지에서 OpsManager 메인 화면으로 가려면 클릭합니다.

        

        e. **Stemcell Library** : Stemcell Library에는 stemcell들을 import 할 수 있습니다. 적용된 stemcell과 stemcell 버전을 확인할 수 있습니다.
더 자세한 정보를 원한다면 Importing and Managing Stemcells을 클릭하세요. (링크 : )

        

        f. **change log** : 이전 설치의 로그를 보고 검색하려면 이 버튼을 클릭합니다. 더 자세한 내용을 확인하고 싶다면 링크(https://docs.pivotal.io/ops-manager/3-0/pcf-interface.html#changelog)를 클릭하세요.

        

        g. **certificates**  : 설치의 인증서를 보려면 이 링크를 클릭합니다. 자세한 내용은 이 항목의 인증서 페이지 섹션을 참조하십시오.(링크 : https://docs.pivotal.io/ops-manager/3-0/pcf-interface.html#certificates)

        

        h. **User Account Menu**: 



        I. **Revert** :



        J. **Review Pending Changes** :



        K.  **Orange Bar** :



        L.  **Missing Stemcell Link** : 



        M. **API Docs** : 



##### Change Log 페이지

- 메인 대시보드 상단 헤더에서 CHANGELOG를 클릭합니다. 이 페이지에는 Ops Manager에서 수행하는 모든 변경 사항 적용 작업 내용이 기록 됩니다.

- 다음표에는 각 Tile에 대한 다음과 같은 최상의 속성이 나열되어 있습니다.

| 상표                | 유형    | 설명                               |
| ----------------- | ----- | -------------------------------- |
| **STATUS**        | Icon  | 배포 성공 또는 실패 여부                   |
| **DEPLOYMENT ID** | Text  | Deployment에 대해 순차적으로 번호가 매겨진 식별자 |
| **USER**          | 사용자 명 | Deployment에 변경 수행한 사용자           |

- LOGS 버튼을 클릭하면 작업 사항에 대한 모든 로그를 보여줍니다.

- 각 작업 목록 내에서  배포되거나 삭제된 개별 제품에 대한 테이블 세부 정보입니다.

| 상표           | 유형                                                           | 설명                                        |
| ------------ | ------------------------------------------------------------ | ----------------------------------------- |
| **PRODUCT**  | Text                                                         | Tile명                                     |
| **ACTION**   | 다음 레이블 중 하나: **ADDED, UPDATED, DELETED, NO CHANGES, FAILED** | 배포 시 Tile과 함께 수행된 작업(있는 경우)               |
| **STARTED**  | UTC 타임스탬프                                                    | Ops Manager가 Tile배포를 시작했을 때               |
| **FINISHED** | UTC 타임스탬프                                                    | Ops Manager가 배포를 중지했거나 Tile 배포를 시도한 경우    |
| **DURATION** | 시간, 분                                                        | Ops Manager가 Tile을 배포하거나 배포를 시도하는 데 걸린 시간 |

* 개별 작업 행 아래의 총계 행에는 **STARTED**, **FINISHED**, 및 **DURATION** 필드에 대한 모든 Tile 총계가 나열됩니다.



##### CERTIFICATES

- 메인 대시보드 상단 헤더에서 CERTIFICATES를 클릭합니다.

- 이 화면에서는 Opsmanager가 관리하는 인증서가 표시됩니다.

- 

---

### 사용 방법 API or CLI

OpsManager를 사용할 때 운영자별로 제한된 액세스 책임을 두어 관리할 수 있습니다.
https://docs.pivotal.io/ops-manager/3-0/opsguide/config-rbac.html







---

### 백업 및 트러블슈팅

### 

---

### 모니터링 및 로깅
