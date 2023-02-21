# TAS

### 개념
--- 
**VMware Tanzu Application Service(TAS)란** 

VMware Tanzu Application Service는 온프레미스와 클라우드 전반에서 마이크로 서비스를 지속적으로 제공하고 대규모로 안전하게 실행하려는 기업을 위한 최신 애플리케이션 플랫폼입니다.

---

**TAS 제공 요소**
- **오픈 소스 코드** : 플랫폼의 개방성과 확장성은 사용자가 단일 프레임워크, 일련의 앱 서비스 또는 클라우드에 갇히지 않도록 합니다.
- **배포 자동화** : 개발자는 기존 도구를 사용하고 코드를 전혀 수정하지 않고 앱을 VM용 TAS에 배포할 수 있습니다.
- **유연한 인프라** : VM용 TAS를 배포하여 자체 컴퓨팅 인프라에서 앱을 실행하거나 vSphere, AWS, Azure, GCP 또는 OpenStack과 같은 IaaS에 배포할 수 있습니다.
- **상용 옵션** : 상용 TAS for VMs 클라우드 공급자가 배포한 PaaS를 사용할 수도 있습니다.
- **커뮤니티 지원** : 광범위한 커뮤니티가 VM용 TAS에 기여하고 지원합니다.
--- 


**TAS 컴포넌트 아키텍처**
![image](https://user-images.githubusercontent.com/66672864/220232756-a31ee17c-c651-4c9b-a10b-65cb8403e283.png)
---


### Routing

- **Router**

  - 사용자 Http 요청 트래픽을 목적지로 라우트하는 역할을 수행합니다. 주 목적지는 Cloud Controller이나 응용애플리케이션을 실행하고 있는 Garden Container 가 됩니다.

- **TCP router**

  - 사용자 Tcp요청 트래픽을 목적지로 라우트하는 역할을 수행합니다. 주 목적지는 응용애플리케이션을 실행하고 있는 Garden Container 가 됩니다.

---

### **Authentication**

 - **UAA**
   - OAuth2 서버 및 로그인 서버로 동작하여 사용자 인증 관리를 제공합니다.

 - **credhub**
   - CredHub는 Ops Manager 배포에서 자격 증명을 생성하고 보호하는 데 도움이 되는 다양한 기능을 수행합니다.

---

### **App Lifecycle**

 - **cloudcontroller**

   - 애플리케이션 스테이징과 실행을 위한 API를 제공합니다.

   - 빌드팩 선정, 서비스와 바인딩, 접근 인가처리와 같은 어플리케이션의 전박적인 관리를 담당합니다.

   - 개발자가 CLI를 통해 명령어를 입력하면 Cloud Controller가 수신합니다.

- **diego brain**
  - ㅁㅁ

- **diego rep**
  - Cell을 대표하며 BBS를 통해 다양한 서비스를 수행합니다
---

### **App Storage & Execution**
 - **blob store**
   - 어플리케이션 패키지, 스테이징된 어플리케이션 droplet, 빌드팩 캐시 등이 저장된 오브제트 저장소입니다.

 - **diego garden**
   - 컨테이너 관리를 위한 플랫폼 독립적인 서버 및 클라이언트 인터페이스를 제공합니다.
---

### **Services**
 - **service brokers**
   - 메세지큐, 데이터베이스와 같은 어플리케이션 실행 시 연동되어 사용되는 서비스를 위해 서비스 인스턴스를 생성합니다.
   - 어플리케이션 서비스를 제공하기 위해 서비스 브로커를 구현하고 서버로 제공합니다.
---

### **Messaging**
 - **service brokers**
---

### **Metrics & Logging**
 - **doppler**
   - Doppler는 애플리케이션 로그를 개발자에게 스트림으로 제공합니다.

 - **log-cache**
   - 로그 캐시를 사용하여 지정된 기간 동안의 로그 및 메트릭을 확인할 수 있습니다. 로그 캐시에는 로그 및 메트릭을 쿼리하고 필터링하는 API 엔드 포인트와 CLI 플러그인이 포함되어 있습니다.

 - **doppler**
   - Doppler는 애플리케이션 로그를 개발자에게 스트림으로 제공합니다.
