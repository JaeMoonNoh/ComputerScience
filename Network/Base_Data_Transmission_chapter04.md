# 데이터 전송 방식

### 전송과 교환

> 교환(Switching)

  * 전달 경로가 둘 이상일 때 라우터에서 데이터를 어느 방향으로 전달할지를 선택하는 기능

> 전송(Transmission)

  * 특정한 물리 매체에 의하여 일대일(1:1)로 직접 연결된 두 시스템 간의 신뢰성 있는 데이터 전송을 보장하기 위한 것이다.

### 전송 방식의 종류

> 지리적 분포에 따라 구분하는 방식

  * LAN(Local Area Network) : 근거리 통신망
  * MAN(Metropolitan Area Network) : 도시 규모의 통신망
  * WAN(Wide Area Network) : 원거리 통신망

> 데이터 전송 교환 기술

  * 점대점 방식(Point to Point) : 각 호스트를 일대일로 직접 연결해 목적지 호스트에만 데이터를 전송하는 방식
    * 송신 호스트가 중개 호스트와 일대일로 연결되므로 다른 호스트에는 데이터가 전달되지 않는다.
    * 인접 호스트에 전송하는 과정을 단계적으로 반복한다.
    * WAN 환경에서 사용
 
  * 브로드 캐스팅(Broad Casting) : 네트워크에 연결된 모든 호스트에 데이터를 전송하는 방식
    * 공유 전송 매체 하나에 여러 호스트를 연결하기 때문에 네트워크에 연결된 모든 호스트에 데이터가 전송된다.
    * 별도의 교환 기능이 필요 없다.
    * LAN 환경에서 사용
 
  * 유니 캐스팅(Uni Casting) : 두 호스트 사이의 데이터 전송을 의미하는 방식
    * 유니포인트(Uni Point) : 수신 호스트 하나와 연결됨
 
 * 멀티캐스팅(Multi Casting) : 다수의 수신 호스트에 전송할 수 있음 
    * 멀티 포인트(Multi Point) : 다수의 수신 호스트와 연결됨

### 오류 제어(Error Control)

  * 프레임 변형 : 데이터가 깨져서 도착함
  * 프레임 분실 : 데이터가 목적지에 도착하지 못함

> 전송 오류의 유형

  * 수신 호스트의 응답 프레임 : 송신 호스트가 전송한 데이터 프레임의 일부가 깨지는 프레임 변형 오류를 확인한 수신 호스트는 송신 호스트에 응답 흐레임을 전송해 원래의 데이터 프레임을 재전송하도록 요구할 수 있다.
    * 긍정 응답 프레임 : 데이터 프레임이 정상적으로 도착했을 때 회신
    * 부정 응답 프레임 : 데이터 프레임이 깨졌을 때 회신
 
  * 송신 호스트의 타이머 기능 : 송신 호스트가 전송한 데이터 프레임이 수신 호스트에 도착하지 못하는 프레임 분실 오류가 발생하면 수신 호스트는 이 사실을 인지할 수 없다.
    * 타임아웃(Time Out) : 데이터 프레임을 전송한 후에 일정 시간 이내에 수신 호스트로부터 긍정/부정 응답 프레임 회신이 없으면 타임아웃 기능을 동작시켜 데이터 프레임을 재전송한다.
  
  * 순서 번호 기능 : 수신 호스트가 보낸 긍정 응답 프레임을 분실하면 데이터 프레임이 제대로 도착해도 송신 호스트가 인지할 수 없다. 따라서 재전송을 통한 데이터 프레임을 중복 수신하는 결과를 초래한다.
    * 순서 번호(Sequence Number) : 중복 데이터 프레임을 가려내려면 각 프레임 내부에 순서번호를 기록해야 한다.

### 흐름 제어(Flow Control)

  데이터 링크 계층에서 제공하는 주요 기능은 데이터 프레임의 전송 속도를 조절하는 것이다. 송신 호스트는 수신 호스트가 감당할 수 있을 정도의 전송 속도를 유지하면서 데이터 프레임을 전송해야 하는데 이러한 기능을 흐름제어라고 한다.
  
  * 흐름제어 기능을 제공하지 않으면 ? 
    수신 호스트는 자신에게 도착한 데이터 프레임을 내부 버퍼에 보관할 여유를 갖지 못하게 된다. 따라서 전송 매체를 통해 올바르게 도착한 프레임이 분실되는 결과를 초래할 수 있다.
