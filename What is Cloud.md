
# 클라우드 기초 개념 정리

# What is Cloud ?   
클라우드는 애플리케이션이 실행되는 환경입니다.  
클라우드 컴퓨팅은 클라우드에서 워크로드를 실행하는 기능, 즉 동작을 말합니다.  
기술은 클라우드를 구축하고 사용하는 데 사용되는 소프트웨어와 하드웨어와 같은 것들입니다   


# Why Cloud ?
---  
- 클라우드 서비스 장점  
    - 민첩성 : 빠른 기술 서비스 적용 가능
    - 탄력성 : 비즈니스 요구가 변화함에 따라 이러한 리소스를 확장하거나 축소 가능
    - 비용 절감 : 본 비용(데이터 센터, 물리적 서버 등)을 가변 비용으로 전환  
  
  
## **Monolithic Architecture** to **Micro Service Architecture**   
`Monolithic Architecture`:  
기존의 웹 시스템 개발 스타일, 하나의 애플리케이션 내에 모든 로직이 들어가있는 구조  
특정 컴포넌트를 수정할 때 수정된 부분만 재배포하는 것이 아니라 전체 어플리케이션을 재컴파일 해서 전체를 다시 통으로 재배포해야함  
but , 규모가 작은 어플리케이션에는 배포가 쉽고, 운영관리가 쉽다. 하나의 구조로 되어있기 때문에 트랜잭션 관리에도 쉽다는 장점. 상황에 따라 MSA와 적절히 섞어 사용  
  
`MSA(Micro Service Architecture)`:  
기존에 하나로 되어있던 어플리케이션을 비즈니스적 관점에서 독립적으로 배포 가능  
실행이 가능한 업무 단위인 마이크로 서비스 블록으로 나눠 이를  Restful API.[^Restful API]
와 같이 심플한 방법으로 상호 통신하고 연계해 응용프로그램을 구성하는 소프트웨어 아키텍처  
-> 유연한 소프트웨어 시스템 개발 운영 가능  
![MSA](https://docs.microsoft.com/ko-kr/azure/architecture/includes/images/microservices-logical.png 'MSA')
  
[^Restful API]:  Rest API (REST = REpresentational State Transfer) : HTTP URI로 정의된 리소스를 HTTP 방식과 페이로드의 결합으로 정의한 API



## Cloud As a Service  
다양한 클라우드 서비스를 용도에 따라 선택하여 사용 가능  
  
![Cloud Service](https://azurecomcdn.azureedge.net/cvt-9963f0986fa62e56a009126ebe6c5cb1175dbfc409c6b78d065d7e54cccfe03f/images/page/overview/what-is-iaas/what-is-iaas.png 'IaaS PaaS SaaS')
![IaaS,PaaS,SaaS](https://ncube-digest.com/wp-content/uploads/2020/02/imgpsh_fullsize_anim.png 'CloudService')  

- Additional Service  
    - CaaS (Container as a Service)  
컨테이너 기반 추상화를 통해 사용자가 애플리케이션을 배포하고 관리하도록 지원하는 클라우드 서비스 컴퓨팅 모델
IaaS 와 PaaS 사이에 존재  
   
    - FaaS (Function as a Service)  
스테이트리스(stateless) 컨테이너에서 실행되는 이벤트 기반 컴퓨팅 실행 모델로서, 서비스를 사용하여 서버측 로직과 상태를 관리
ex)AWS Lambda



## 클라우드 주요 기술 4가지  
![클라우드 주요 기술](https://ditoday.com/wp-content/uploads/2019/11/1-1.jpg)  

<br>  
- Container vs. VM  
vm이 container보다 훨씬 더 강력하게 격리됩니다.   
vm은 가상화된 하드웨어 위에 os가 올라가는 형태로 거의 완벽하게 host와 분리된다고 봐도 무방
반면 container는 os 가상화입니다. os 부분을 가상화해서 올리고 커널을 host와 공유합니다.  vm보다 얕게 격리.
![컨테이너](https://developer.ibm.com/kr/wp-content/uploads/sites/98/container1-1.png)  

<br>
 
- MSA(Micro Service Architecture)  
기존에 하나로 되어있던 어플리케이션을 비즈니스적 관점에서 독립적으로 배포 가능, 실행이 가능한 업무 단위인 마이크로 서비스 블록으로 나눠 이를  Restful API와 같이 심플한 방법으로 상호 통신하고 연계해 응용프로그램을 구성하는 소프트웨어 아키텍처  
-> 유연한 소프트웨어 시스템 개발 운영 가능
    - 기존의 Monolithic Architecture  
    ![Monolithic](http://postfiles2.naver.net/MjAxOTA1MTVfODAg/MDAxNTU3OTIxOTE4MDIz.DsYooBXd_-wH2kE6uUavOuStF84FLvQgZPaAfzvXAXEg.H6t9zx3HX4WCyre_AbkVpF243D-K1_ji-Z7tZlvjMVAg.PNG.kbh3983/Screen_Shot_2019-05-15_at_9.04.56_PM.png?type=w773)  
    - 효율적인 Micro Service Architecture  
    ![MSA](http://postfiles6.naver.net/MjAxOTA1MTVfMjUg/MDAxNTU3OTIwNjU2NDcx.eKMhKtoET8F43F7BAHJX3O2nITapnmmMbExmmzX94m0g.sLYx2RNI5aVI551PfifzT6-zxKgNUsLpopNIRvgK2VYg.PNG.kbh3983/Screen_Shot_2019-05-15_at_8.43.42_PM.png?type=w773)

<br>

- DevOps
development(개발)’와 'operations(운영)  
DevOps는 소프트웨어 시스템을 빠르고 고품질로 개발 웅연하기 위한 조직문화이자 접근 방식
개발 조직, 운영 조직, 품질 조직들은 공동의 목표를 설정, 이를 달성하기 위한 자동화 도구 및 시각화 지표 활용하여 소프트 웨어 시스템의 빠른 개발과 운영이 가능   
![DevOps](https://nickjanetakis.com/assets/blog/cards/what-is-devops-c1c3c2a09afea5f71fa738b5431a41cda923cd9e8795cf67dc5cfa2966f61ccd.jpg)
<br>

- CI/CD (Continuous Integration/ Continuous Delivery or Deployment)  
어플리케이션 개발 단계를 자동화하여 애플리케이션을 보다 짧은 주기로 고객에게 제공하는 방법.
지속적인 통합, 지속적인 서비스 제공, 지속적인 배포   
애플리케이션의 라이프사이클 전체에 걸쳐 지속적인 자동화와 지속적인 모니터링을 제공합니다.  
=> CI/CD 파이프라인 : 개발 및 운영팀의 `애자일 방식`[^애자일 방식] 협력을 지원  
![CI/CD](https://i0.wp.com/www.docker.com/blog/wp-content/uploads/4fa92c35-5a00-4e7a-929e-e5ae4b99701a.jpg?fit=1600%2C902&ssl=1)
[^애자일 방식]:애자일 개발의 핵심은 작동하는 소프트웨어의 작은 구성 요소를 신속하게 제공하여 고객의 만족도를 개선
