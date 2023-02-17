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

- 캡쳐 + 작성 예정

---

### 

### 업그레이드 방법

- ㄹ

---

### 사용 방법 UI

이 단계에서는 OpsManager 인터페이스의 주요 기능에 대해 설명합니다.

- [Using the Ops Manager Interface](#Opsmanager-인트페이스-사용법)
- [Reviewing Pending Product Changes](#Preview-Pending-Changes-사용법)
- [Adding and Deleting Products](#Products-추가-및-삭제)
- [Importing and Managing Stemcells](#Stemcells-가져오기-및-관리)
- [Managing Errands in Ops Manager](#Opsmanager에서-Errand-관리)

##### Opsmanager 인트페이스 사용법

###### 메인페이지

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

###### Change Log 페이지

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

###### CERTIFICATES

- 메인 대시보드 상단 헤더에서 CERTIFICATES를 클릭합니다.

- 이 화면에서는 Opsmanager가 관리하는 인증서가 표시됩니다.

<캡쳐>

- **인증서** 페이지 의 상단 섹션 에는 Ops Manager API가 교체하려고 시도하는 인증서가 포함되어 있습니다. 이 섹션에는 Ops Manager API가 교체할 수 있는 인증서와 수동으로 교체해야 하는 인증서가 모두 포함되어 있습니다.

- 이러한 인증서를 교체하는 방법에 대한 자세한 내용은 [인증서 교체 개요를](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.10/vmware-tanzu-ops-manager/security-pcf-infrastructure-api-cert-rotation.html) 참조하십시오.

- **다음은 인증서** 페이지 에 나열된 정보에 대한 설명입니다 .
  
  - **Certificate name:** **인증서** 의 이름입니다.
  
  - **Product GUID:** 고유 식별자가 있는 Tile의 이름입니다.
  
  - **Location:** CredHub 또는 Ops Manager가 인증서를 저장하고 관리하는지 여부입니다.
  
  - **Type:** 인증 기관(CA) 또는 Leaf 인증서인지 여부입니다.
  
  - **Configurable:**  인증서를 구성할 수 있는지 여부입니다. 인증서를 구성할 수 있는 경우 고유한 인증서를 생성하여 Ops Manager 구성 창에 붙여넣을 수 있습니다.
  
  - **Valid until:** 인증서가 만료되는 날짜입니다.

<캡쳐>

- 다음 이미지는 **인증서** 페이지 의 **제외된 인증서** 섹션을 보여줍니다.
  
  - **제외된 인증서** 섹션 에는 CredHub Maestro CLI를 사용하여 교체해야 하거나 Ops Manager API가 교체를 시도하지 않는 인증서가 포함되어 있습니다.
  
  - 서비스 TLS CA 및 해당 Leaf 인증서는 CredHub Maestro CLI를 사용하여 순환해야 합니다. 서비스 TLS CA 인증서 및 해당 Leaf 인증서를 순환하려면 *CredHub Maestro를 사용한 고급 인증서 순환* 에서 [서비스 TLS CA 및 해당 리프](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.10/vmware-tanzu-ops-manager/security-pcf-infrastructure-advanced-certificate-rotation.html#services-rotation) 인증서 순환을 참조하십시오 .
  
  - **제외된 인증서** 에 나열된 다른 모든 인증서 의 경우 회전 불가 인증서와 연결된 제품 타일에 대한 설명서를 참조하거나 Support 에 문의 하십시오.

###### Settings Page

화면 오른쪽 상단에 있는 사용자 이름을 클릭 하고 설정 을 선택하여 **Settings** 페이지로 이동 **합니다** . 

※ Note *:  Settings에서 설정하는 정보를 적용하기 위해 Apply Chnages 버튼을 클릭할 필요가 없습니다. 이러한 설정은 Opsmanager VM에 적용됩니다. Bosh Director가 이러한 설정을 배포에 적용하지 않습니다.*

- **Change Decryption Passprase**
  
          <캡쳐>
  
  - 복호화 암호를 재설정하려면 다음과 같이 세부 정보를 입력하고 **Change Decryption Passphrase** 를 클릭하십시오 .
  
  - Current Decryption Passphrase :  현재 암호 해독 암호
  
  - New Decryption Passphrase : 새 암호 해독 암호
  
  - Confirm New Decryption Passphrase : 새 암호 해독 암호            

- **Internal Authentication Settings**
  
  **내부 인증 설정** 창을 사용 하여 내부 인증 방법에 대한 설정을 보고 업데이트할 수 있습니다.
  
  이 창에는 다음 필드가 포함됩니다.
  
  - Current Decryption Passphrase : 내부 인증 방법에 대한 암호 해독 암호를 업데이트합니다.
  
  - Admin Username : 관리 사용자의 사용자 이름을 업데이트합니다.
  
  - Admin Password : admin 사용자의 비밀번호를 업데이트합니다.

- **SAML Settings**
  
  ID 공급자(IdP)를 SAML로 변경하려면 다음 필드를 구성하십시오.
  
  - Current Decryption Passphrase : **현재 암호 해독 암호** 를 입력합니다.
  
  - SAML IDP Metadata : 전체 URL 또는 XML SAML IdP 메타데이터를 입력합니다.
  
  - BOSH IDP Metadata : (선택 사항) 전체 URL 또는 XML BOSH IdP 메타데이터를 입력합니다. 비워 두면 기본값은 위의 필드와 동일한 메타데이터입니다.
  
  - SAML Admin Group :  모든 Ops Manager 관리자를 포함하는 SAML 그룹의 이름을 입력합니다. 이 필드는 대소문자를 구분합니다.
  
  - Groups Attribute :  SAML 서버를 구성한 그룹 속성 태그 이름을 입력합니다. 이 필드는 대소문자를 구분합니다.
  
  - Provision an admin client in the Bosh UAA : BOSH UAA에서 관리 클라이언트를 프로비저닝하려면 활성화하십시오. 자세한 내용 *은 BOSH Director용 UAA 클라이언트 생성 의* [Admin 클라이언트 프로비저닝](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.10/vmware-tanzu-ops-manager/install-opsmanager-create-bosh-client.html#saml) 을 참조하십시오 .

- **LDAP Settings**

        이 창을 사용하여 IdP를 LDAP로 변경합니다.

        IdP를 SAML 또는 LDAP로 변경하는 방법에 대한 자세한 내용은 IaaS 구성에 대한 다음 지침을 참조하십시오. [Configuring BOSH Director on vSphere](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.10/vmware-tanzu-ops-manager/vsphere-config.html)

- **SSL Certificate**
  
  [캡쳐]

        **SSL 인증서** 창을 사용하여 UI 및 API를 통한 모든 Ops Manager 트래픽에 사용자 지정 SSL 인증서를 사용하도록 Ops Manager를 구성 할 수 있습니다 .

        이 창에는 다음 필드가 포함됩니다.

         **Certificate** : 사용자 지정 인증서를 입력합니다.

        **Private Key :** 인증서의 개인 키를 입력합니다.

        필드를 비워 두면 Ops Manager는 자체 사용자 지정 인증서 및 개인 키가 아닌 자동 생성된 자체 서명 인증서를 사용합니다. 사용자 지정 인증서를 자체 서명된 인증서로 바꾸려면 자체 서명된 인증서로 **Revert to self-signed certificate**를 선택 합니다.        

   

- **VMware Tanzu Network Settings**

        [VMware Tanzu 네트워크 API](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/2.10/vmware-tanzu-ops-manager/install-add-delete.html#pivnet-api) 토큰을 입력 하고 토큰 **추가** 를 클릭 하여 **설치 대시보드** 를 VMware Tanzu 네트워크 에 연결하십시오 .

- **Proxy Settings**
  
  프록시를 사용하여 Ops Manager에 연결 하는 경우 **HTTP 프록시** , **HTTPS 프록시** 또는 **프록시 없음** 을 제공 하여 **프록시 설정** 을 업데이트하십시오 .

- **Custom Banner**

        운영자에게 중요한 메시지를 전달하는 사용자 지정 텍스트 배너를 만듭니다. **UI 배너** 에 대해 Ops Manager UI의 각 페이지에 표시할 텍스트를 입력합니다 . **SSH 배너** 의 경우 운영자가 Operations Manager VM에 접속할 때 표시되는 텍스트를 입력합니다.

- **Export Installation Settings**

        모든 정보와 함께 현재 설치를 내보냅니다. 설치를 내보낼 때 내보낸 파일에는 기본 VM 이미지, 필수 패키지 및 구성 설정에 대한 참조가 포함됩니다.

- **Syslog**

        관리자만 볼 수 있습니다. Ops Manager용 사용자 지정 Syslog 서버를 구성합니다. **예** 를 선택 하고 다음 필드를 채우면 Ops Manager는 Ops Manager VM의 모든 syslog 항목을 생성하여 구성된 syslog 엔드포인트로 보냅니다. Ops Manager는 또한 BOSH Director 액세스 이벤트를 syslog 엔드포인트로 보냅니다.

※ Note *:   Ops Manager syslog 항목은 RFC 3164 형식으로 전송됩니다.*

    Ops Manager 로그에 대한 사용자 지정 syslog 엔드포인트를 구성하려면:                   

1. **Syslog** 를 선택 합니다.

2. (선택 사항) **예** 를 선택하여 Ops Manager 시스템 로그를 원격 서버로 보냅니다.

3. **주소에 원격 서버의 IP 주소** 또는 DNS 이름을 입력합니다 .

4. 포트에 원격 서버가 청취하는 포트 번호를 입력 **하십시오** .

5. **전송 프로토콜** 드롭다운 에서 **TCP** 또는 **UDP** 를 선택 합니다. 이 선택은 원격 서버에 로그를 보내는 데 사용되는 전송 프로토콜을 결정합니다.

6. (선택 사항) TLS를 사용 하여 원격 서버에 암호화된 로그를 보내려면 **TLS 활성화 확인란을 선택합니다.** 확인란을 선택한 후:
   
   1. **Permitted Peer** 에 원격 피어의 이름 또는 SHA1 지문을 입력합니다 .
   2. SSL 인증서 에 원격 서버의 SSL 인증서를 입력 **합니다** .

7. (선택 사항) Queue Size 에 정수를 입력합니다 . 이 값은 버퍼에 보관된 로그 메시지 수를 지정합니다. 기본값은 100,000입니다.

8. (선택 사항) **디버그 로그** 를 외부 소스로 전달 확인란을 선택합니다. 이 옵션은 기본적으로 선택 취소되어 있습니다. 선택하면 대량의 로그 데이터가 생성될 수 있습니다.

9. **(선택 사항) Custom rsyslog 구성** 필드 에 rsyslog에 대한 구성 세부 정보를 입력합니다 . 이 필드에는 rainerscript 구문이 필요합니다.

10. **SAVE** 를 클릭 합니다.
- **Advanced Options**
  
  - **활동 데이터** 다운로드: 설치를 위한 구성 파일, 배포 기록 및 버전 정보가 포함된 디렉터리를 다운로드합니다.
  
  -  **루트 CA 인증서 다운로드:** Ops Manager API를 컬링하는 대신 배포의 루트 CA 인증서를 다운로드하는 데 사용합니다.
  
  - **이 설치** 삭제: Ops Manager 설치를 영구적으로 삭제합니다.
  
  - **진단 보고서 보기:** 배포 구성에 대한 다양한 유형의 정보를 표시합니다.

###### My Account Page

<캡쳐>

이메일과 암호를 변경하려면 화면 오른쪽 상단 모서리에 있는 사용자 이름을 클릭하고 **My Account**를 클릭하고 내 계정 페이지로 이동합니다.

- **Profile**: 현재 이메일 주소와 가려진 비밀번호가 표시됩니다.
- **Third Party Access**: 사용이 승인된 모든 제3자 애플리케이션이 여기에 나열됩니다.
- **Change Email**
- **Change Password**

##### Preview Pending Changes 사용법

이 항목에서는 ****Review Pending Changes**** 페이지와 VMware Tanzu Operations Manager(Ops Manager)에서 개별 Tile 또는 여러 Tile을 선택적으로 배포하는 방법에 대해 설명합니다. Tile을 선택적으로 배포하면 배포 시간을 크게 줄일 수 있습니다.

<캡쳐>

###### Review Pending Changes Page

- **A**—**Select All Products:** 활성화되면 확인란이 사용 가능한 모든 Tile을 선택합니다. 체크박스를 선택 해제하면 사용 가능한 모든 Tile이 선택 해제됩니다.

- **B**—**Select Product:** 각 제품 목록 옆에 있는 확인란을 사용하여 배포하려는 Tile을 선택할 수 있습니다. BOSH Director는 항상 선택됩니다.

- **C**—**Product Listing:**  각 Tile 목록에는 배포를 위해 준비된 Tile 버전이 표시됩니다. 각 목록의 상단에는 다음 세 가지 색상 중 하나가 표시됩니다.
  
  - 초록색 : Tile이 구성되었으며 배포할 준비가 되었습니다.
  
  - 주황색 : Tile이 완전히 구성되지 않았으며 아직 배포할 수 없습니다.
  
  - 빨강색 : Tile이 삭제 대기 중입니다.

- **D**—**Depends on:** 이 섹션에는 Tile 종속성 및 버전이 나열됩니다. 종속성이 있는 Tile을 배포하도록 선택한 경우 해당 Tile의 모든 종속성도 동일한 배포에 배포해야 합니다. 종속성은 다음 색상으로 표시됩니다.
  
  - 초록색 : 올바른 버전의 종속성이 설치 되었습니다.
  
  - 빨간색 : 종속성의 호환되지 않는 버전이 설치 되어있습니다. 빨간색 텍스트에(optional)이 선택되어 있다면 변경 사항을 계속 적용할 수 있습니다.
  
  - 회색 : 종속성이 설치되지 않았지만 선택 사항입니다.

- **E**—**Warnings:** 주황색 Tile 목록의 빨간색 텍스트는 Tile을 배포하기 전에 변경해야 함을 나타냅니다. 다음 경고 중 일부가 표시될 수 있습니다.
  
  - **Missing stemcell(s)** : Stemcell Library에서 하나 이상의 stemcell을 선택해야합니다.
  
  - **Stemcell(s) out of date**: Stemcell Library에서 Tile에 대해 하나 이상의 stemcell 을 업데이트 해야합니다. 자세한 내용은 [Importing and Managing Stemcells](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/opsguide-managing-stemcells.html)를 참고하세요.
  
  - **Configuration is incomplete** : Tile 구성을 완료해야 합니다.
  
  - **Configuration is invalid** : Tile의 잘못된 구성을 해결해야 합니다.

- **F**—**Changes:**  이 섹션에는 Ops Manager가 아직 배포를 시도하지 않은 Tile에 대한 상위 수준의 보류 중인 변경 사항이 나열됩니다. Ops Manager가 Tile 배포를 시도하지만 배포에 실패하면 이 목록이 지워지고 다음 배포를 위해 보류 중인 변경 사항이 유지됩니다. Tile이 성공적으로 배포되었는지 확인하려면 [변경 로그 페이지를](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/pcf-interface.html#changelog) 참조하십시오. 나열된 변경사항은 아래와 같습니다.
  
  - Tile 삭제가 준비되었습니다.
  
  - Tile 버전이 업데이트 되었습니다.
  
  - Stemcell이 추가되었습니다.
  
  - Stemcell이 업데이트 되었습니다.

- **G**—**Errands:** 이 섹션을 확장하면 해당 Tile이 배치될 때 트리거되는 Errand를 활성화하거나 비활성화할 수 있습니다. 예를 들어 Errand를 활성화하여 속성을 기록할 수 있습니다. 자세한 내용은 [Ops Manager에서 Errand 관리를](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/install-managing_errands.html) 참조하십시오.

- **H**—**Staged:** 이 섹션은 Tile 상태를 나타냅니다.

- **I**—**See Changes:** 이 버튼을 클릭하면 해당 Tile에 대한 보류 중인 변경사항을 볼 수 있습니다.

- **J**—**Apply Changes:** 이 버튼을 클릭하면 활성화된 모든 Tile이 배포됩니다.

###### About Pending Changes for a Specific Tile

배포에서 Tile의 구성을 변경한 경우 **Pending Changes** 페이지를 사용하여 기존 매니페스트 또는 구성에 대한 변경 사항을 한 줄씩 검토합니다.

이 페이지에는 기존 Tile 구성에 대한 단계적 변경 사항이 요약되어 있습니다. 이 페이지에 표시된 변경 사항은 아직 Tile 배포에 적용되지 않았습니다.

이 페이지에서 운영자는 Tile 배포에 변경 사항을 적용하기 전에 단계적 변경 사항을 승인할 수 있도록 매니페스트 및 구성에 대한 변경 사항을 확인할 수 있습니다.

###### Use the Pending Changes Page

변경 요약 필드에는 Ops Manager UI 또는 API를 사용하여 활성화 또는 비활성화된 기능이 표시됩니다. 이러한 변경 사항은 단계적이지만 아직 구현되지 않았습니다. **이러한 변경 사항을 적용** 하려면 변경 사항 적용을 클릭해야 합니다 .

특정 Tile에 대한 변경 사항을 보려면:

1. 보류 중인 변경 사항 검토 페이지에서 검토하려는 타일의 **See Changes**를 클릭합니다. 새 탭이 열립니다.

2. 표시된 변경 사항을 검토합니다. 비활성화 된 설정은 빼기 기호(-)와 함께 빨간색으로 표시됩니다. 활성화 된 설정은 더하기 기호(+)와 함께 녹색으로 표시됩니다.

3. 탭을 닫고 보류 중인 변경 사항 검토 페이지로 돌아가 변경 사항을 적용하거나 다른 Tile을 검토합니다.

<캡쳐>

위는 BOSH Director 의 매니페스트에 대한 변경 사항을 보여줍니다.

타일을 변경하면 다음 Tile 영역에 대한 변경 요약이 표시됩니다.

- Manifest

- Runtime configs

- CPI configs

- Cloud configs

만약 Tile 변경 사항이 없으면 `No changes`라고 보여집니다.

※ Note *:   Errand 변경 사항은 페이지 UI에 표시되지 않습니다.*

##### Products 추가 및 삭제

Opsmanager에 Products를 추가하고 삭제하는 방법에 대해 설명합니다.

※ Note *:   Opsmanager에서는, 모든 product tile은  기본적으로 floating stemcells을 사용합니다. 이렇게 하면 Tile이 최신 패치 버전의 stemcell을 자동으로 사용하도록 하여 배포 보안이 강화되지만 Tile 업그레이드에 필요한 시간이 크게 늘어날 수 있습니다. 자세한 내용은 [Floating Stemcells](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/install-understanding-stemcells.html)를 참고하세요.*

###### Add and Import Products

Ops Manager 설치에 Tile을 추가하거나 가져오려면:

1. [VMware Tanzu 네트워크](https://network.pivotal.io/) 에서 제품을 다운로드하십시오.

2. Ops Manager 설치 대시보드로 이동하여 로그인합니다.

3. **Import a Product** 클릭합니다 .

4. `.pivotal`VMware Tanzu Network에서 다운로드했거나 소프트웨어 배포자로부터 받은 파일을 선택 하고 **열기를** 클릭합니다 . 제품이 성공적으로 추가되면 **제품 가져오기** 버튼 아래 제품 목록에 나타납니다. 선택한 제품이 최신 버전이 아닌 경우 제품 목록에 최신 버전이 나타납니다.

5. 제품 목록의 오른쪽 하단에 있는 녹색 **+ 아이콘을 클릭하여 Ops Manager 설치 대시보드에 제품 타일을 추가합니다.**

6. Ops Manager 설치 대시보드에 제품 타일이 나타납니다. 제품에 구성이 필요한 경우 타일 하단의 막대가 주황색으로 나타납니다. 필요한 경우 제품을 구성합니다.

7. (선택 사항) 제품 구성 설정에서 **Errands** 창을 선택하여 설치 후 Errand를 구성하거나 기본 설정을 검토합니다. 설치 후 Errand는 제품 설치 후 Ops Manager가 제품을 사용할 수 있게 만들기 전에 자동으로 실행되는 스크립트입니다. 설치 후 Errand에 대한 자세한 내용은 Ops Manager Tile 개발자 가이드의 [Errands](http://docs.pivotal.io/tiledev/tile-errands.html)를 참조하세요.

<캡쳐>

     위 캡쳐는 Broker Registar 체크 박스 예시 입니다. 이 errand registers 서비스 브로커 확인란을 활성화하면 이 errand는 클라우드 컨트롤러에 서비스 브로커를 등록하고 이전 등록 이후 변경된 모든 브로커 URL 및 자격 증명 값을 업데이트합니다.

    8. **Review Pending Changes**를 클릭합니다.

    9. **Apply Changes**클릭하여 설치를 시작하고 제품에 대한 설치 후 lifecycle errands를 실행하십시오.

###### Using the VMware Tanzu Network API to Upgrade Products (제외 -> 인터넷 불가)

Opsmanager 설치에서 각각의 새 버전의 제품을 수동으로 다운로드하는 대신 API 토큰을 사용하여 Opsmanager 설치 대시보드를 VMware Tanzu 네트워크와 연결하여 제품을 업그레이드할 수 있습니다. 제품을 업로드하면 이후의 모든 제품 업그레이드가 Opsmanager 설치 대시보드에 자동으로 나타납니다.

###### BOSH Director에 변경 사항 적용

새 Opsmanager 설치에서 또는 업그레이드의 일부로 여러 제품을 스테이징할 때 Opsmanager 설치 대시보드의 보류 중인 변경 사항 **Review Pending Changes** 화면에서 변경 사항을 BOSH Director에만 적용할 수 있습니다.

###### Delete Products

Opsmanager 설치에서 제품을 삭제하려면:

설치 대시보드에서:

1. 해당 제품을 제거하려면 제품 Tile에서 휴지통 아이콘을 클릭하십시오.
2. 표시되는 **Delete Product** 대화 상자에서 **Confirm**을 클릭합니다.

※ Note *:  BOSH Director 제품은 삭제할 수 없습니다.*

3. **Review Pending Changes**를 클릭하고 **Apply Changes**를 클릭합니다.

제품을 삭제하면 제품 타일이 설치 및 설치 대시보드에서 제거됩니다. 그러나 해당 제품은 Available Products view에 나타납니다.

##### Stemcells 가져오기 및 관리

이 항목에서는 VMware Tanzu Operations Manager(Opsmanager)에서 Stemcell Library를 사용하여 Stemcell를 제품으로 가져오고 스테이징하는 방법에 대해 설명합니다.

###### Overview

Stemcell Library는 Stemcell를 제품으로 가져오기 위해 준비합니다.

For more conceptual information about floating stemcells and stemcell upgrades, see [Floating Stemcells](https://docs.pivotal.io/platform/customizing/understanding-stemcells.html). 

※ Note *:  일부 제품 릴리즈에는 Opsmanager에서 Xenial Stemcell를 사용하는  Tile에 나열된 대로 Xenial Stemcell이 필요합니다. Xenial Stemcell를 처음 가져왓 사용하는 경우 [Xenial Stemcell지원 업데이트를](https://docs.pivotal.io/pivotalcf/2-3/pcf-release-notes/breaking-changes.html#xenial) 참조하십시오 .*

###### Import and Stage a Stemcell

Stemcell을 가져오고 준비하려면 다음을 수행해야합니다.

1. VMware Tanzu Network에서 .tgz 확장자를 가진 Stemcell 파일을 다운로드합니다.

2. Stemcell import를 클릭하여 Stemcell를 Opsmanager로 가져옵니다. IMPORT STEMCELL 대화 상자가 나타납니다.

3. 스테이징할 제품을 선택합니다.

<캡쳐>

4. **APPLY STEMCELL TO PRODUCTS**를 클릭하거나 **Dismiss**를 클릭하여 대화 상자를 닫습니다.

###### Choose a Stemcell Version

만약 여러 버전의 stemcell을 업로드하였다면, **Staged** 열의 드롭다운 메뉴를 사용하여 사용할 버전을 선택할 수 있습니다.

배포하기 전까지 다른 버전을 선택할 수 있습니다. 배포 후에는 이전 stemcell 버전을 더 이상 사용할 수 없습니다. 업그레이드 전에 업로드한 stemcell을 사용하려면 Opsmanager를 업그레이드 한 후 다시 업로드 해야합니다.

<캡쳐>

Stemcell이 녹색 체크 표시와 스테이징 됨 과 함께 **Latest stemcell** 이라는 단어가 보이게 되면, stemcell이 호스트에서 사용 가능한 최신 버전입니다. 오래된 Stemcell은 **Stemcell-out-of-date** 라고 표시됩니다.

<캡쳐>

##### Opsmanager에서 Errand 관리

###### Overview

Opsmanager에서 제품 errands를 어떻게 사용하는지와 그것을 어떻게 구성해야 하는지에 대해 설명합니다.

Errand는 설치된 제품이 사용 가능 시간 시작될 때와 끝날 때 실행할 수 있는 스크립트입니다. Opsmanager를 사용하여 이러한 Errand 실행 여부와 시기를 조정할 수 있습니다.

제품 타일에는 두 가지 유형의 Errand가 포함됩니다.

- **Post-deploy errands** : 제품이 설치 된 후 Opsmanager가 제품을 사용할 수 있게 만들기 전에 실행 됩니다. Errand 기능 중 하나의 예로 마켓플레이스에 새로 설치 된 서비스를 게시합니다.

- **Pre-delete errands** : 운영자가 제품 삭제를 선택한 후 Opsmanager가 실제로 제품을 삭제하기 전에 실행됩니다. 한 예로 Errand에 사용된 모든 데이터 개체를 제거하는 정리 작업을 수행합니다.

**Review Pending Changes**를 클릭 후 Opsmanager에서 변경 사항을 적용하기 위해 **Apply Changes**를 클릭하면 BOSH는 실행되는 각 Errand에 대한 VM을 생성하거나 기존 VM에서 Errand를 배치합니다. Tile에는 BOSH가 제품의 Errand를 배치하는 위치를 결정되어 있습니다.

VMware Tanzu Application Service for VMs(TAS for VMs)는 스모크 테스트, 앱 관리자, 알림, Opsmanager 계정 및 자동 확장 Errand를 포함하여 여러 가지 배포 후 Errand를 제공합니다. VM용 TAS Errand에 대한 자세한 내용은 [VM용 TAS 구성을](https://docs.pivotal.io/application-service/operating/configure-pas.html) 참조하십시오 .

###### Errand Run Rules

운영자는 Errand를 위해 **ON, OFF** 2가지로 설정 가능합니다. 이러한 규칙은 Opsmanager가 Errand를 실행하는 시기를 제어합니다.

Errand가 ON으로 구성되면 제품 manifest에 변경 사항이 없어도 항상 실행됩니다. Errand가 OFF로 구성된 경우 실행되지 않습니다.

###### Opsmanager 기본 설정과 Tile 기본 설정

기본적으로 Opsmanager는 모든 errand에 ON 규칙을 적용합니다.

###### Configure Run Rules in Ops Manager

###### Errand Pane:Persistent Rules

<캡쳐>

###### Pending Changes: One-Time Rules

###### 

---

### API or CLI 사용방법

OpsManager를 사용할 때 운영자별로 제한된 액세스 책임을 두어 관리할 수 있습니다.
https://docs.pivotal.io/ops-manager/3-0/opsguide/config-rbac.html

- [Using Ops Manager Programmatically and from the Command Line](#CLI를-사용하여-Opsmanager-사용)
- [Using the Ops Manager API](# Opsmanager-API-사용)
- [Using the Ops Manager CLI](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/install-cli.html)

##### CLI를 사용하여 Opsmanager 사용

이 항목에서는 Opsmanager UI가 아닌 CLI에서 프로그래밍 방식으로 VMware Tanzu Operations Manager(Opsmanager) 작업을 실행하기 위한 세 가지 도구인 Ops Manager API, 명령줄 인터페이스(CLI) 및 플랫폼 자동화 작업을 소개합니다.

###### Overview

- Opsmanager API. 자세한 내용은 [Ops Manager API](https://docs.pivotal.io/platform/opsman-api) 문서를 참조하세요.

- 명령어  `om` CLI 에 대한 자세한 내용은  [`om` repository](https://github.com/pivotal-cf/om) 를참조하십시오 .

- 플랫폼 자동화 작업. 자세한 내용은 [플랫폼 자동화](http://docs.pivotal.io/platform-automation) 설명서를 참조하십시오.

이 세 가지 도구는 서로 다른 추상화 수준에서 Ops Manager VM을 제어합니다. 플랫폼 운영자는 아래와 같이 사용합니다.

###### Opsmanager API

###### Opsmanager CLI(om)

###### Platform Automation

###### Examples of Equivalent Operations

##### Opsmanager API 사용

Opsmanager API는 Opsmanager UI를 우회하여 Opsmanager VM을 직접 제어합니다.

플랫폼 운영자는 Ops Manager API를 사용하여 배포를 자동화하고, 자격 증명을 검색 및 관리하고, Opsmanager와 함께 작업합니다.  Ops Manager API에 대한 자세한 내용은 [Ops Manager API](https://docs.pivotal.io/ops-manager/3-0/api) 설명서를 참조하십시오. 

###### Related Tools

명령줄 또는 쉘 스크립트내에서 Opsmanager 를 작업하는 경우 일반적으로 Opsmanager CLI인 om을 사용합니다. 이는 Opsmanager API를 사용하는 것 보다 더 편리합니다.

###### Opsmanager API에 액세스

Opsmanager API에 액세스하려면 Opsmanager 사용자 계정 및 인증(UAA) 서버에 인증하고 아래 단계에 따라 로그인해야합니다.

- UAAC 설치

    아직 UAAC를 설치 하지 않은 경우 아래 단계를 진행합니다.

    `gem install cf-uaac`

- 인증 토큰 검색 

    [Using the Ops Manager API](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/install-ops-man-api.html)

---

### 백업 및 트러블슈팅

### 

---

### 모니터링 및 로깅
