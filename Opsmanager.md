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

 

- [Using the Ops Manager Interface](#Opsmanager-인터페이스-사용법)
- [Reviewing Pending Product Changes]
- [Adding and Deleting Products](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/install-add-delete.html)
- [Importing and Managing Stemcells](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/opsguide-managing-stemcells.html)
- [Managing Errands in Ops Manager](https://docs.vmware.com/en/VMware-Tanzu-Operations-Manager/3.0/vmware-tanzu-ops-manager/install-managing_errands.html)



##### # Opsmanager 인터페이스 사용법

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



##### REVIEW PENDING CHANGES Page

이 항목에서는 ****Review Pending Changes**** 페이지와 VMware Tanzu Operations Manager(Ops Manager)에서 개별 Tile 또는 여러 Tile을 선택적으로 배포하는 방법에 대해 설명합니다. Tile을 선택적으로 배포하면 배포 시간을 크게 줄일 수 있습니다.





---

### 사용 방법 API or CLI

OpsManager를 사용할 때 운영자별로 제한된 액세스 책임을 두어 관리할 수 있습니다.
https://docs.pivotal.io/ops-manager/3-0/opsguide/config-rbac.html

---

### 백업 및 트러블슈팅

### 

---

### 모니터링 및 로깅
