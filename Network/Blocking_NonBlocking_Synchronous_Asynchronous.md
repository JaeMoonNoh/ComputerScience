# Blocking & Non - Blocking

  * 호출된 함수가 호출한 함수에게 제어권을 건네주는 유무의 차이
  * 다른 주체가 작업할 때 자신의 제어권이 있는지 없는지 확인하는 차이

## Blocking

![Blocking](https://user-images.githubusercontent.com/62277037/145331167-2d763e9a-626d-4c25-b233-1adb90e40c06.PNG)

> 함수 A,B가 있고, A안에서 B 함수를 호출했다고 가정

  * A 함수는 함수 B가 내 할일을 다 마칠 때까지 제어권을 가지고 있는다.
  * A는 B가 다 마칠때 까지 기다려야 한다.

## Non - Blocking

![Non_blocking](https://user-images.githubusercontent.com/62277037/145331170-383dfdc9-4360-4b7e-9012-13452bb8150c.PNG)

> 함수 A,B가 있고, A안에서 B 함수를 호출했다고 가정

  * 함수 B는 할일을 다 마치지 않았더도 A에게 제어권을 바로 넘겨주게 된다.
  * A는 B를 기다리면서도 다른 일을 진행이 가능합니다.


# Synchronous & Asynchronous

  * 동시성이 중요하다.
  * 호출된 함수 B를 호출한 함수 A가 신경을 쓰는지의 여부
  * 호출된 함수 B가 스스로 신경 쓰는지를 동기 / 비동기라고 생각을 하면 됩니다.
  * 결과가 나왔을 때 순서와 결과에 관심이 있는지 아닌지 판단


## Synchronous

![Synchronous](https://user-images.githubusercontent.com/62277037/145331159-552f9f84-678f-43dd-a7ac-eb44af893092.PNG)

  * 함수 A는 함수 B가 일을 하는 중에 기다리며, 현재 상태가 어떤지 계속해서 체크를 한다.

## Asynchronous

![Asynchronous](https://user-images.githubusercontent.com/62277037/145331166-600544b4-3517-4b18-af27-319f939c35f1.PNG)

  * 함수 B의 수행상태를 B 혼자 직접 신경 쓰며 처리를 한다.
  * 비동기는 호출시 Call Back을 전달하여 작업의 완료 여부를 호출한 함수에게 답함

    * Call Back
      * 다른 함수의 인자로써 이용되는 함수
      * 어떤 이벤트에 의해 호출되어지는 함수


## Sync~

![synchnonsync](https://user-images.githubusercontent.com/62277037/145331786-0b39eb56-7564-4cc2-9948-cf0a414e8676.PNG)
