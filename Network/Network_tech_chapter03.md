# Network Tech

> 교환 시스템

  * 네트워크 양단에 연결된 호스트들이 전송하는 패킷은 전송 경로 중간에 위치한 교환 시스템을 거친다.
  * 데이터를 최종 목적지까지 올바른 경로로 중개하는 교환 기능을 제공한다.

> 회선 교환(Circuit Switching)

  * 호스트가 데이터를 전송하기 전에 연결 경로를 미리 설정하는 방식
  * 연결 성정 과정에서 송수신 호스트 간의 경로가 결정되기 때문에 모든 데이터가 같은 경로로 전달된다.
  * 고정 대역의 논리적인 전송 선로를 전용으로 할당받으므로, 안정적인 데이터 전송률을 지원한다.
  * 패킷으로 전송되지 않는다는 점이 가상 회선 방식과의 차이점이다.

> 메시지 교환(Message Switching)

  * 데이터를 전송하기 전에 경로를 미리 설정하지 않고, 대신 전송하는 메시지의 헤더마다 목적지 주소를 표시하는 방식이다.
  * 교환 시스템에서 전송 데이터를 저장하는 기능을 제공한다.
  * 위와 같은 기능 때문에 송신 호스트가 보낸 시점과 수신 호스트가 받은 시점이 반드시 일치할 필요가 없다.

> 패킷 교환(Packet Switching)

  * 패킷이라는 일정 크기로 나우어 전송하며, 각 패킷은 독립적으로 라우팅 과정을 거쳐 목적지에 도착한다.
  * 전송대역의 효율적 이용, 호스트의 무제한 수용, 패킷에 우선순위 부여의 장점이 있다.

> 가상 회선 방식(Virtual Circuit)

  * 연결을 통해 전송되는 모든 패킷의 경로가 동일하다.
  * 송수신 호스트 사이에 설정된 가상의 단일 파이프를 통해 송신 호스트가 입력단으로 패킷을 송신하고, 수신 호스트가 출력단에서 패킷을 수신한다.
  * 모든 패킷이 하나의 파이프로 표현되는 동일 경로로 전송되므로 패킷이 도착하는 순서가 보낸 순서와 같다.
  * 파이프는 한 프로세스의 출력을 다른 프로세스의 입력으로 사용할 수 있도록 프로세스를 연결하는 논리적 통신 매체이다.

> 데이터그램(Datagram)

  * 비연결형 서비스를 이용해 패킷을 독립적으로 전송하는 것이다.
  * 패킷을 송신하기 전에 연결을 설정하는 과정이 없으므로, 미리 경로를 할당하지 않는다.
  * 전송되는 패킷들은 독립적인 경로로 전달된다.
  * 일반적으로 전송할 정보의 양이 적거나 상대적으로 신뢰성이 중요하지 않은 환경에서 사용된다.(UDP)

# 인터 네트워킹

둘 이상의 서로 다른 네트워크를 연결하는 기능이다.

> 라우터(router)
  
  * 3 Layer(Network) 기능을 지원한다.
  * 교환 기능을 수행할 수 있으므로 여러 포트를 사용해 다수의 LAN을 연결하는 구조를 지원한다.
  * 수신한 패킷을 해석해 적절한 경로로 전송하도록 경로를 배정하는 기능을 한다.
  * 하위 3개 계층인 물리 계층, 데이터 링크 계층, 네트워크 계층의 기능을 수행하며, 특별히 네트워크 계층까지의 기능을 수행하는 장비이다.

> 네트워크 간의 차이

  * 연결형/ 비연결형 서비스
  * 데이터 전송에 사용되는 프로토콜 종류
  * 호스트를 구분하기 위한 주소 표현 방법
  * 전송 패킷의 크기
  * 멀티 캐스팅 브로드 캐스팅의 지원 여부

> 리피터(Repeater)

  * 1 Layer(Physical) 기능을 지원한다.
  * 한쪽 단에서 들어온 비트 신호를 증폭하여 다른 단으로 단순히 전달하는 역할이다.

> 브리지(Bridge)

  * 2 Layer(Data Link) 기능을 지원한다.
  * 한쪽 단에서 들어온 프레임의 MAC 계층 헤더를 다른 단의 MAC 계층 헤더로 변형해 전송할 수 있다.
  * 송수신 호스트의 위치가 서로 다른 LAN에 속하면 중개 기능을 수행한다.

# 인터넷 라우팅

> 고정 경로 배정(Fixed Routing)
 
  * 송수신 호스트 사이에 영구불변의 경로를 배정한다.
  * 단점은 전송 경로가 고정되므로 트래픽 변화에 따른 동적 경로 배정이 불가능하다.

> 적응 경로 배정(Adaptive Routing)

  * 인터넷 연결 상태가 변하면 이를 데이터그램의 전달 경로에 반영한다.
  * 경로 결정과정에 영향을 주는 요소는 특정 네트워크나 라우터가 정상적으로 동작하지 않는 경우, 네트워크의 특정 위치에서 
