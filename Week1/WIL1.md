# 1. MVC 패턴이란?

MVC는 Model, View, Controller의 약자로, 어플리케이션의 구성요소를 세가지 역할로 구분한 패턴이다. 사용자로부터의 요청은 Controller에서 받아 어떻게 처리할 지 결정한다. 이후 Model에서 데이터베이스를 처리한다. 이를 가지고 View를 통해 시각화 하는 것이다. 

Model은 데이터를 처리하는 영역으로 데이터를 가진 객체라고 볼 수 있다. 그렇기에 Model은 사용자가 원하는 모든 데이터를 가지고 있어야 한다. Model에 변화가 있을 때 Controller과 View에 이를 통보하고 사용자 요청이 있을 때 이를 수신하지만 View와 Controller에 대한 정보는 알면 안된다. 즉 데이터 변경이 있을 때 Model이 직접 수정할 수 있게 View, Controller을 참조해서는 안된다는 것이다.

View는 데이터를 보여주는 화면이다. HTML, CSS, Javascript 등을 통해 보여준다. View는 별도로 데이터를 저장하지 않고 단지 보여주기만 할 뿐이다. 그러므로 View도 다른 구성요소의 정보를 몰라야 한다.

Controller은 Model, View와 소통하며 사용자와 데이터 간 다리 역할을 한다. 사용자 입력이 있을 때 이에 대한 응답으로 Model과 View를 업데이트한다. 즉 사용자의 요청은 Controller에 의해 처리된다. 그렇기에 Controller은 Model, View에 대한 정보를 가지고 있어야 한다. 또한 Model, View의 모니터링을 통해 수정 요청이 있을 때 각 구성요소에 통지할 수 있어야 한다.

 그렇다면 이 MVC 패턴은 왜 필요할까? 그건 각 영역을 분할함으로써 서로 간의 의존성을 낮출 수 있기 때문이다. 이렇게 독립적인 영역으로 구성되면 각 영역 간 분업 및 협업이 원활해지는 장점이 있다.  

 # 2. API와 서버?

API는 “Application Programming Interface”의 약자로 서로 다른  애플리케이션에서 데이터를 읽고 쓸 때, 서로간 상호작용을 용이하게 한다. 이 예로 기상청의 소프트웨어 시스템에는 날씨 데이터가 있다. 그리고 휴대폰의 날씨 앱은 API를 통해 기상청의 소프트웨어 시스템과 소통하여 휴대폰에 날씨 정보를 표시한다. 

서버는 서비스를 제공하는 소프트웨어, 클라이언트는 서비스를 사용하는 소프트웨어라고 생각할 수 있다. 즉 클라이언트가 요청을 하고 서버는 그에 따른 응답을 하는 셈이다. 이렇게 요청을 받아 응답을 하는 과정을 서비스라고 한다. 서버는 다양한 형태로 구성될 수 있는다. 그 예로 웹서버, 데이터베이스서버 등이 있다.

API는 클라이언트와 서버의 관점에서 생각해볼 수 있다. 요청을 보내는 앱을 클라이언트라고 생각하면, 응답을 보내는 앱이 서버라고 할 수 있다. 위의 예시에서 기상청의 데이터베이스가 서버이고, 휴대폰 앱은 클라이언트인 셈이다.

# 3. RESTful 이란?

REST는 “Representational State Transfer”의 약자로, 각 자원을 구분하여 해당 자원의 상태를 주고받는 모든 것을 의미한다. 즉 HTTP URI(Uniform Resource Identifies)를 통해 자원(Resource)을 명시하고, HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 통해 해당 URI에 대한 CRUD Operation을 적용하는 것이다. 여기서 CRUD Operation이란 Create, Read, Update, Delete의 기능을 일컫는 말이다. REST는 HTTP 프로토콜 인프라를 사용하므로 REST API를 위한 별도의 인프라를 구축할 필요가 없다는 장점이 있다.

RESTful 은 REST원리를 따르는 시스템을 뜻한다. RESTful API는 두 시스템이 인터넷을 통해 정보를 안전하게 교환하기 위해 사용하는, REST를 기반으로 한 API이다. 

