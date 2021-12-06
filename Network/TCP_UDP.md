# TCP(Transmission Control Protocol) / UDP(User Datagram Protocol)


## TCP(Transmission Control Protocol)

  * 연결지향적
  * 데이터 전달 보증이 확실하다
  * 순서보장을 한다.

## 3way handshake

* 서버가 활성화된 상태가 아니라면 데이터를 보내도 의미가 없다. 해당 서버가 활성화 되어있는지 인증을 받고 보내는 절차이다.

![3way](https://user-images.githubusercontent.com/62277037/144814385-e7826eb5-4d50-4e40-9730-13175db865e2.PNG)


## 4way handshake

* 세션을 종료하기 위한 절차이다(Session Layer가 있음)

![4way](https://user-images.githubusercontent.com/62277037/144814391-c7a501b5-0b3c-47e6-b8e6-1f30078ea1de.PNG)

## UDP(User Datagram Protocol)

  * TCP의 기능이 제공되지 않는다.
  * 기능이 적은 대신 단순하고 빠르다.
  * IP에 Port와 CheckSum 기능만 제공을 한다.
    * port : 한 서버에 여러가지 요청을 할 때 각각의 출입문을 만드는 과정, 원하는 기능으로 가기 위해 port에 입장을 한다.
  
