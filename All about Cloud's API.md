
### All about Cloud's API  

#### 원격 API (Application Programming Interface)
원격 API는 커뮤니케이션 네트워크를 통해 상호 작용하도록 설계되었습니다.  
여기서 '원격'이란 API에 의해 조작되는 리소스가 요청을 보내는 컴퓨터의 외부에 있음을 의미합니다.  
가장 광범위하게 사용되는 커뮤니케이션 네트워크가 인터넷이기 때문에 대부분의 API는 웹 표준을 기반으로 설계되며, 모든 원격 API가 웹 API인 것은 아니지만 웹 API가 원격이라고 가정할 수는 있습니다.  

웹 API는 일반적으로 요청 메시지에 HTTP를 사용하여 응답 메시지 구조의 정의를 제공합니다. 이러한 응답 메시지는 일반적으로 XML 또는 JSON 파일의 형태입니다. 다른 애플리케이션이 쉽게 조작할 수 있는 방식으로 데이터를 표시하므로 XML과 `JSON` 둘 다 자주 사용됩니다.  
<br> 

#### JSON ? 
- JSON (JavaScript Object Notation)  

- JSON이란 경량의 데이터 교환 형식으로 프로그래밍 언어가 아닌 단순히 데이터를 표시하는 표현 방법, 데이터 포맷입니다.  
자바스크립트 (Javascript)에서 객체를 만들 때 사용하는 표현식을 의미합니다.
`AJAX`로 서버와 통신하며 데이터를 주고 받을 때 데이터 교환을 쉽게 하기 위해 JSON을 사용합니다.  
    ##### AJAX란?  
Ajax는 JavaScript의 라이브러리중 하나이며 `Asynchronous` Javascript And Xml(비동기식 자바스크립트와 xml)의 약자입니다. 브라우저가 가지고있는 XMLHttpRequest 객체를 이용해서 전체 페이지를 새로 고치지 않고도 페이지의 일부만을 위한 데이터를 로드하는 기법 이며,  
Ajax를 한마디로 정의하자면 JavaScript를 사용한 비동기 통신, 클라이언트와 서버간에 XML 데이터를 주고받는 기술이라고 할 수 있겠습니다.

        ※ 비동기(async)방식이란?  
비동기 방식은 웹페이지를 리로드하지 않고 데이터를 불러오는 방식입니다. 이 방식의 장점은 페이지 리로드의 경우 전체 리소스를 다시 불러와야하는데 이미지, 스크립트 , 기타 코드등을 모두 재요청할 경우 불필요한 리소스 낭비가 발생하게 되지만 비동기식 방식을 이용할 경우 필요한 부분만 불러와 사용할 수 있으므로 매우 큰 장점이 있습니다.  

<br> 

### REST API (Representational State Transfer)   
#### REST ? 
###### REST의 정의   
“Representational State Transfer” 의 약자  
- REST 구성 요소
    - 자원(Resource): URI  
        - 모든 자원에 고유한 ID가 존재하고, 이 자원은 Server에 존재한다.  
        - 자원을 구별하는 ID는 ‘/groups/:group_id’와 같은 HTTP URI 다.  
        - Client는 URI를 이용해서 자원을 지정하고 해당 자원의 상태(정보)에 대한 조작을 Server에 요청한다.
    - 행위(Verb): HTTP Method  
        - HTTP 프로토콜의 Method를 사용한다.  
        - HTTP 프로토콜은 GET, POST, PUT, DELETE 와 같은 메서드를 제공한다.  
    - 표현(Representation of Resource)  
        - Client가 자원의 상태(정보)에 대한 조작을 요청하면 Server는 이에 적절한 응답(Representation)을 보낸다.  
        - REST에서 하나의 자원은 JSON, XML, TEXT, RSS 등 여러 형태의 Representation으로 나타내어 질 수 있다.  
        - JSON 혹은 XML를 통해 데이터를 주고 받는 것이 일반적이다.    
        

###### REST의 구체적인 개념  
- HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고, HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미한다.  
- 즉, REST는 자원 기반의 구조(ROA, Resource Oriented Architecture) 설계의 중심에 Resource가 있고 HTTP Method를 통해 Resource를 처리하도록 설계된 아키텍쳐를 의미한다.
- 웹 사이트의 이미지, 텍스트, DB 내용 등의 모든 자원에 고유한 ID인 HTTP URI를 부여한다.
> CRUD Operation  
Create : 생성(POST)  
Read : 조회(GET)  
Update : 수정(PUT)  
Delete : 삭제(DELETE)  
HEAD: header 정보 조회(HEAD)  

#### RESTful API ?
웹 API가 확산됨에 따라, 과거에는 SOAP(Simple Object Access Protocol) 프로토콜 방식을 사용했습니다.  
최근에는 REST 아키텍처의 제약 조건을 준수하는 웹 API인 RESTful API를 사용하고 있습니다.
다음 6가지 제약 조건을 지키기만 하면 RESTful API라 할 수 있습니다.  
<br> 
- 클라이언트 서버 아키텍처: REST 아키텍처가 클라이언트, 서버, 리소스로 구성되며 HTTP를 통해 요청을 처리합니다.  

<br> 
- 스테이트리스: 요청이 통과하는 서버에는 클라이언트 콘텐츠가 저장되지 않으며 그 대신 세션 상태에 대한 정보가 클라이언트에 저장됩니다.  *예) http*  
    * 참고) 네트워크 계층 내, 전송 계층에서 사용하는 프로토콜 - TCP / UDP 통신 :
    TCP: 연결형 서비스-연속성보다 신뢰성있는 전송이 중요할 때에 사용하는 프로토콜  
    UDP: 비연결형 서비스-신뢰성보다는 연속성이 중요한 서비스  
    
        *참고 URL: [네트워크 계층](https://needjarvis.tistory.com/158)*
<br> 
- 캐시 가능성: 캐싱으로 일부 클라이언트-서버 간의 상호 작용이 제거됩니다.  
<br> 
- 계층화된 시스템: 추가 계층으로 클라이언트-서버 간의 상호 작용을 조정할 수 있으며 이러한 계층은 로드 밸런싱, 공유 캐시 또는 보안과 같은 추가 기능을 제공할 수 있습니다.  
<br> 
- 코드 온디맨드(옵션): 서버가 실행 가능한 코드를 전송하여 클라이언트의 기능을 확대할 수 있습니다.  
<br> 
- 통합된 인터페이스: 이 제약 조건은 RESTful API 설계의 핵심이며 다음과 같은 4가지 측면을 포함합니다.    
    <br>  
    - 요청에서 리소스 식별: 리소스가 요청에서 식별되며 클라이언트로 반환된 표현으로부터 분리됩니다.

    - 표현을 통한 리소스 조작: 클라이언트가 리소스를 나타내는 파일을 수신합니다. 이 표현에는 조작 또는 삭제를 허용할 수 있도록 충분한 양의 정보가 포함되어야 합니다.

    - 자기 기술적(Self-descriptive) 메시지: 클라이언트에 반환되는 각 메시지에 클라이언트가 정보를 어떻게 처리해야 할지 설명하는 정보가 충분히 포함되어야 합니다.

    - 애플리케이션 상태 엔진으로서의 하이퍼미디어: 리소스를 할당한 후 REST 클라이언트가 하이퍼링크를 통해 현재 사용 가능한 기타 모든 작업을 찾을 수 있어야 합니다.   
    <br>  
![RESTful API](https://gmlwjd9405.github.io/images/network/restful.png)  
    <br>  
    
> **REST API 장점**  
- HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요가 없다.
- HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
- HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
- Hypermedia API의 기본을 충실히 지키면서 범용성을 보장한다.
- REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
- 여러가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
- 서버와 클라이언트의 역할을 명확하게 분리한다.  

> **REST API 단점**
- 표준이 존재하지 않는다.
- 사용할 수 있는 메소드가 4가지 밖에 없다.
- HTTP Method 형태가 제한적이다.
- 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 값이 왠지 더 어렵게 느껴진다.
- 구형 브라우저가 아직 제대로 지원해주지 못하는 부분이 존재한다.
- PUT, DELETE를 사용하지 못하는 점
- pushState를 지원하지 않는 점

[출처: Rest API 상세](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)
