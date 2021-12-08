# Proxy & Balancing

* Proxy Server : 클라이언트와 서버간의 중계서버로, 통신을 대리 수행하는 서버입니다.
* Balancing : 한대의 서버 컴퓨터만으로 다수의 클라이언트를 수용할 수 없기 때문에, 적절하게 다른 서버로 배치해주는 방법

## Load_Balancing
![LoadBalancing](https://user-images.githubusercontent.com/62277037/145144476-4c04e272-4357-42c4-9122-4d962e3f3a8e.PNG)

 * Load Balancing : 여러 서버에 부하를 나누어주는 역할을 한다. 서비스를 운영하는 사이트의 규모에 따라 웹 서버를 추가로 증설하면서 로드 밸런서로 관리해주며 웹 서버의 부하를 해결한다.

증가하는 클라이언트에 대한 모든 트래픽을 1대의 서버 컴퓨터로 감당할 수 없기때문에 서버를 다루는 2가지 방법이 있습니다.

  * Scale-up : 하드웨어의 성능을 올리는 방법
  * Scale-out : 여러대의 서버가 나눠서 일하도록 하는 방법

하드웨어의 성능을 올리는 방법(Scale-up)은 비용이 많이 들고, 서버를 여러대로 증설(Scale-out)을 하면 무중단 서비스를 제공하는 환경 구성이 용이하다.
이 상황에서 여러 서버에게 균등하게 트래픽을 분산시켜주는 장치가 Load Balancing 입니다.


## Forward_Proxy
![ForwardProxy](https://user-images.githubusercontent.com/62277037/145144480-2f845ea8-72c8-4928-925c-d14a37bd9e25.PNG)

계속해서 서버에 정보를 요청하는 것은 전송시간이 오래 걸릴 뿐더러, 외부 요청도 늘어나게 되어있어 Forward_Proxy를 사용해 문제를 해결한다

  * Caching : 클라이언트와 요청한 내용을 캐싱(잠시 저장)
    * A 클라이언트가 날씨를 요청하면 잠시 캐시에 저장을 해두었다가, B 클라이언트가 같은 요청을 하게 되면 캐시에서 꺼내 전달한다.

  * 익명성 : 클라이언트가 보낸 요청을 감춘다. 클라이언트의 정보가 아닌 Forward Proxy의 정보를 전달하고, 서버가 받은 요청을 누가 보냈는지 알지 못하게 합니다.

  * 전송시간이 절약
  * 불필요한 외부 전송을 하지 않음
  * 외부 요청 감소
  * 네트워크 병목 현상 방지
  * 서버가 받은 요청을 누가 보냈는지 알지 못하게 합니다.

## Reverse_Proxy
![ReverseProxy](https://user-images.githubusercontent.com/62277037/145144482-ab28fd12-f2e1-4e7e-8c8f-5258814bcd66.PNG)

  * Caching : Forward와 동일
  * 보안 : 서버 정보를 클라이언트로부터 숨기고, 클라이언트는 Reverse Proxy를 실제 서버라고 생각해 요청하기 때문에 서버의 IP가 노출되지 않는다.
