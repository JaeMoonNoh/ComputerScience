# 병행 프로세스 (Parallel_process)

> 병행 프로세스의 해결 과제

  * 공유 자원을 상호 배타적으로 사용해야 한다. 예를 들어, 프린터, 통신망 등은 한순간에 프로세스 하나만 사용해야 한다.
  * 병행 프로세스 간에는 협력이나 동기화가 되어야 한다. 상호배제도 동기화의 한 형태이다.
  * 두 프로세스 사이에서는 데이터를 교환할 수 있도록 통신이 되어야 한다.
  * 프로세스는 동시에 수행하는 다른 프로세스의 실행 속도와 관계없이 항상 일정한 실행 결과를 보장하도록 결정성을 확보해야한다.
  * 교착 상태를 해결하고 병행 프로세스들의 병렬 처리 능력을 극대화 해야한다.
  * 병행 프로세스를 수행하는 과정에서 발생하는 상호배제, 즉 어떤 프로세스가 작업을 싱핼 중일때 나머지 프로세스는 그것과 관련된 작업을 수행할 수 없도록 보장해야한다.

# 상호배제와 동기화

> 상호배제(Mutual Exclusion)

  * 병행 프로세스에서 프로세스 하나가 공유 자원을 사용할 때 다른 프로세스들이 동일한 일을 할 수 없도록 하는 방법이다.
  * 공유 자원에 있는 데이터에 접근하는 다른 프로세스를 프로세스 하나가 해당 데이터에 접근할 수 없게 하는 것

> 상호배제 4가지 조건

  * 두 프로세스는 동시에 공유 자원에 진입할 수 없다.
  * 프로세스의 속도나 프로세서 수에 영향을 받지 않는다.
  * 공유 자원을 사용하는 프로세스만 다른 프로세스를 차단할 수 없다.
  * 프로세스가 공유 자원을 사용하려고 너무 오래 기다려서는 안된다.

> 상호배제 방법들

  * 데커의 알고리즘 : 두 프로세스가 동시에 임계 영역에 진입하려고 시도하면 순서에 따라 오직 하나만 임계 영역에 들어가도록 허용한다.

> 뮤텍스(Mutex)

  * 오직 하나의 Process, Thread만이 동일한 시점에 Mutex를 얻어 임계영역에 들어오게 된다. 오직 이 Process, Thread만이 임계영역에서 나갈때 Mutex 해제가 된다.(1개의 lock만 갖는다.)

> 세마포(Semaphore)

  P(Proberen) : 검사 
  V(Verhogen) : 증가 
  S(Semaphore) : 세마포

  * 진입 조건을 반복 조사하지 않고 True일 때 프로세스 상태를 확인한다면 프로세서 사이클을 낭비하지 않을 것이다.
  * Multi Programming 환경에서 공유자원에 대한 접근을 제한하는 방법이다.
  * 공유자원을 안전하게 관리한다.
  * Counting Semaphore (계수 세마포) : 유한한 자원에 접근하는 것을 제어할 수 있으므로, 여러 번 획득하거나 해제할 수 있도록 count를자원의 사용 허가 값으로 사용한다. 스레드 프로세스가 count 이상이 접근하면 lock을 실행한다.
  * Binary Semaphore (이진 세마포) : 세마포의 카운트가 1이며 뮤텍스처럼 사용이 가능하다.

> 모니터가 나오게 된 계기
   
   * 모든 프로세스가 1로 초기화한 세마포를 공유하고, 임계 영역에 진입하기 전에는 signal 연산을 실행한 후 wait 연산을 실행해야 한다. 이 순서를 따르지 않으면 두 프로세스가 동시에 임계 영역에 있을 수 있다.
   * wait과 signal 연산 순서를 바꿔 실행하거나 둘 중 하나 이상을 생략하면 상호배제를 위반하거나 교착 상태가 발생한다.
   * wait와 signal 연산이 프로그램 전체에 퍼져 있고 이들 연산이 각 세마포에 주는 영향을 전체적으로 파악하기 어렵다
   
> 모니터란?
  * 모니터는 일반 컴퓨터 모니터가 아니라 핸슨이 제안하고 호가 수정한 공유 자원과 이것의 임계 영역을 관리하는 소프트웨어 구성체이다.
  * 사용자 사이에서 통신하려고 동기화하고, 자원에 배타적으로 접근할 수 있도록 프로세스가 사용하는 병행 프로그래밍 구조이다.
  * 모니터는 공유데이터, 임계영역이 코딩된 프로시저, 초기화 코드로 구성된 모듈이다.
  * 모니터의 권한을 부여하지 않은 프로세스들은 준비 큐에서 진입을 기다리게 하여 상호배제를 실현한다.

  
> 동기화

  * 공유 자원을 동시에 사용하지 못하게 실행을 제어하는 방법
  * 동기화는 순차적으로 재사용 가능한 자원을 공유하려고 상호작용하는 프로세스 사이에서 나타난다.
  * 위의 과정에서 교착 상태와 기아 상태가 발생할 수 있다.

> 임계 자원(critical resource)

  * 두 프로세스가 동시에 사용할 수 없는 공유 자원

> 임계 영역(critical resource)

  * 임계 자원에 접근하고 실행하는 프로그램 코드 부분
  * 프로세스가 공통 변수를 읽고, 테이블을 갱신하고, 파일을 수정하는 등 공유 데이터에 접근할 때 임계 영역에 있다.
  * 다수의 프로세스가 접근할 수 있지만, 어느 한순간에는 프로세스 하나만 사용할 수 있다.
  * 반드시 한 번에 프로세스 하나만 진입할 수 있어야 한다.
  * 작업을 빠르게 수행하고, 특정 프로세스가 임계 영역에 오래 머물거나 무한 루프 등에 빠지지 않게 해야한다.
  * 동시 접근시 잘못된 결과가 발생한다.
  * 실행중 중단하지 못한다.


