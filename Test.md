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


### Routing

**Router**

사용자 Http 요청 트래픽을 목적지로 라우트하는 역할을 수행합니다. 주 목적지는 Cloud Controller이나 응용애플리케이션을 실행하고 있는 Garden Container 가 됩니다.

**TCP router**

사용자 Tcp요청 트래픽을 목적지로 라우트하는 역할을 수행합니다. 주 목적지는 응용애플리케이션을 실행하고 있는 Garden Container 가 됩니다.

### **Authentication**

**uaa**

OAuth2 서버 및 로그인 서버로 동작하여 사용자 인증 관리를 제공합니다.
