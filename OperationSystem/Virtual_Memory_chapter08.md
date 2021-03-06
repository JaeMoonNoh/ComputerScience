# 가상 메모리 (Virtual Memory)

메모리를 관리하는 또 다른 형태, 각 프로그램이 실제 메모리 주소가 아닌 가상 메모리 주소를 주는 방법이다.
다중 프로그래밍 환경에서 흔히 사용하며, 메인 메모리보다 더 큰 저장 공간을 제공하는 방법이다.

  * 사용자와 논리적 주소를 물리적으로 분리하여 사용자가 메인 메모리 용량을 초과한 프로세스에 주소를 지정해서 메모리를 제한 없이 사용할 수 있도록 하는 개념
  * 프로그램 전체를 동시에 실행하지 않으므로 요구한 메모리 전체가 아닌 일부만 적재해도 실행이 가능하다.
  * 활동 영역을 메인 메모리에 유지하면서 필요할 때는 디스크와 메모리 사이에 프로세스 코드와 데이터를 저장한다.
  * 자동으로 스왑인, 스왑 아웃 과정을 거쳐 프로세스를 재할당한다.
  * 디스크에 저장된 주소 공간은 캐시로 처리하여 메인 메모리를 효율적으로 사용할 수 있게 한다.

process 전체가 메모리 내에 올라오지 않더라도 실행이 가능하게 하는 작업, 주기억장치 이용률과 다중 프로그램이 요율을 높인다.

  * 사용자가 물리 메모리의 제약에서 벗어나게 합니다.
  * 각 프로그램이 더 작은 메모리를 차지하기 때문에 더 많은 프로그램을 동시에 수행(시분할 형식)
  * 프로그램을 메모리에 올리고 스왑하는데 필요한 I/O 횟수가 줄어듭니다.

### 가상메모리가 성공적인 이유

  * 예외를 처리하는 오류 처리 코드는 자주 필요하지 않으며, 발생하지 않을 수 있다.
  * 배열, 리스트, 테이블 등은 실제로 사용한 크기보다 항상 더 크게 정의 될 수 있다.
  * 선택한 메뉴 하나만 메인 메모리에 적재하고 나머지는 메인 메모리에서 내보내도 된다.

> 논리적 주소, 프로그램 주소

  실행중인 프로세스가 참조하는 주소

> 매핑(mapping)

  가상 주소를 물리적 주소로 변환하는 과정, MMU(Memory Management Unit)이라는 HW에 의해 지원된다.


### 요구 페이징(Demand Paging)

  프로그램의 일부만 메인 메모리에 적재하되, 순차적으로 작성되어 있는 프로그램의 모듈을 처리할 때 다른 부분은 실행하지 않는다는 특징을 이용한다.
  
  * 실행 중인 프로세스들의 요구 페이지만 메모리에 반입(Fetch)하여 프로세스의 모든 페이지를 메로리에 동시에 적재하지 않는다.
  * 동적 주소 변환에서는 가상 메모리와 메인 메모리의 매핑을 매핑 테이블로 표시하고, 페이지 방법에서는 페이지 테이블로 표시한다.
  * Valid, inValid bit를 추가 한다.

### 페이지 부재(Page Fault)

  프로그램이 메모리에 저장되지 않은 페이지를 사용하려고 할때 발생한다.

### 페이지 대체 알고리즘

> 선입선출 대치 알고리즘(FIFO, First In, First Out)


> 최적 페이지 대치 알고리즘(OPT, Optimal replacement)


> 최근 최소 사용 대치 알고리즘(LRU, Least Recently Used)


> NUR 알고리즘(Not used Recently)


>
