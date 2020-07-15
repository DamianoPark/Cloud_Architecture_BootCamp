
### API GateWay VS Service Mesh  
|  | API Management | Service Mesh 
|--- |--- |---
|라우팅 주체|서버|요청하는 서비스
|라우팅 구성요소|별도의 네트워크를 도입하는 독립적인 API gateway 구성요소|서비스 내 sidecar로 Local network 스택의 일부가 됨
|로드 밸런싱|단일 엔드포인트를 제공하고, API Gateway 내 로드밸런싱을 담당하는 구성요소에 요청을 redirection하여 해당 구성요소가 처리함|Service Registry에서 서비스 목록을 수신함. sidecar에서 로드밸런싱 알고리즘을 통해 수행함
|네트워크|외부 인터넷과 내부 서비스 네트워크 사이에 위치함|내부 서비스 네트워크 사이에 위치하며, 응용프로그램의 네트워크 경계 내에서만 통신을 가능하게 함
|분석|API에 대한 사용자 및 공급자에 대한 모든 호출에 대해 수집되고 분석됨|Mesh 내 모든 마이크로서비스 구성요소에 대해 분석가능  

<br>  

- API 게이트 웨이  
![API 게이트웨이](https://media.vlpt.us/post-images/tedigom/78ec1240-fd32-11e9-ba49-23d182ee1325/apigateway.png)  

<br>  

- 서비스 메시  
![서비스 메시](https://media.vlpt.us/post-images/tedigom/3fbe7db0-0925-11ea-aa94-f3699ad0167a/service-mesh-generic-topology.png)

- API Gateway -> Sevice Mesh  
![Total](https://media.vlpt.us/post-images/tedigom/87e37700-083d-11ea-bf9d-db5436d09a81/servicemesh-apigateway.png)  

<br> 

[참조 : API Gateway vs Service Mesh 차이](https://velog.io/@tedigom/MSA-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-4Service-Mesh-f8k317qn1b#:~:text=%EC%B5%9C%EA%B7%BC%20MSA%EC%97%90%EC%84%9C%20API%20Gateway,%EA%B5%AC%EC%A1%B0%EB%A1%9C%20%EB%A7%8E%EC%9D%B4%20%EC%82%AC%EC%9A%A9%EB%90%98%EA%B3%A0%20%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4.)    
<br>  

#### Service Mesh 좀더 깊게 알아보기   
- Service mesh 유형  
    - 1) PaaS (Platform as a Service)의 일부로 서비스 코드에 포함되는 유형  
    Microsoft Azure Service fabric, lagom, SENECA 등이 이 유형에 해당되며, 프레임워크 기반의 프로그래밍 모델이기 때문에, 서비스메쉬를 구현하는데에 특화된 코드가 필요합니다. ( Mesh-native Code )

    - 2) 라이브러리로 구현되어 API 호출을 통해 Service mesh에 결합되는 유형  
    Spring Cloud, Netflix OSS(Ribbon/Hystrix/Eureka/Archaius), finagle 등이 이 유형에 해당되며, 프레임워크 라이브러리를 사용하는 형태입니다.  
    이중 Netfilix의 Prana는 sidecar 형태로 동작합니다. 서비스 메시를 이해하고 코드를 작성해야합니다. (Mesh Aware Code)

    - 3) Side car proxy를 이용하여 Service mesh를 마이크로서비스에 주입하는 유형  
    `Istio` /Envoy, Consul, Linkerd 등이 이 유형에 해당되며, sidecar proxy 형태로 동작됩니다. 따라서 서비스메시와 무관하게 코드를 작성할 수 있습니다.  
    Istio와 같은 Service Mesh 프레임워크들은 다음과 같은 기능들을 지원하고 있습니다.   *가장 많이 추천 되는 유형*   
        - Sidecar pattern?  
            - Sidecar는 서비스에 들어오거나 나가는 모든 네트워크 트래픽을 처리  
            - 비즈니스 로직이 포함된 실제 서비스와 sidecar이 병렬로 구성  
            -> 서비스 호출에서 서비스가 직접 서비스를 호출하는 것이 아니라 proxy 를 통해서 호출
            - 따라서, 대규모의 마이크로서비스 환경이라고 하여도 개발자가 별도의 작업 없이 서비스의 연결 뿐만 아니라, 로깅, 모니터링, 보안, 트래픽 제어와 같은 다양한 이점을 누릴 수 있습니다.  
        ![사이트카](https://media.vlpt.us/post-images/tedigom/ac3a3bd0-092c-11ea-8263-c5a6e835ad0d/sidecar.png)  

<br>  

- 서비스 메시 기능
    - Service Discovery
    - Load balancing (지연시간 기반 / 대기열 기반 )
    - Dynamic Request Routing  
    - Circuit Breaking  
    - 암호화 (TLS)  
    - 보안  
    - Health check, Retry and Timeout  
    - Metric 수집  

<br>  

- Istio 로 구성된 서비스 메시 예시  
![service mesh](https://user-images.githubusercontent.com/15958325/70860649-7c8e1400-1f67-11ea-8897-abc3f55ff788.png)

<br>  

- 추가 : 프록시란? Proxy  
        프록시 : [대신하다]  
    프록시의 단어 의미와 같이, 프로토콜에 있어서 대리 응답 등에 사용하는 `개념`  
보안상의 문제로 직접 통신을 주고 받을 수 없을 때 프록시를 이용하여 `중계를 기능` 합니다.  
    
