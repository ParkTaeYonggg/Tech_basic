# Tech_basic 자바스크립트 기초
## this
this는 참 어렵다. 쉽게 생각해 this는 this를 불러낸 함수를 나타낸다.


<img width="300" alt="스크린샷 2021-12-13 오후 5 37 18" src="https://user-images.githubusercontent.com/86910922/145778924-cb246471-f1dd-4e90-a3aa-073dfd16942e.png">
<img width="300" alt="스크린샷 2021-12-13 오후 5 37 12" src="https://user-images.githubusercontent.com/86910922/145778932-b7e65f0d-0179-47ec-93b7-02fa643fde49.png">

위처럼 fn1에서의 메서드는 this를 찍어보면 자신을 불러낸 함수를 쳐다보고 있다. <br>
그치만 fn2는 fn1에 있긴 하지만 따로 만들어지고 불려진 존재이다.<br>
따로 만들어진 fn2는 당연히 fn1을 감싸는 함수 내에서 실행된 것이니 fn1을 감싸는 함수를 바라볼 것이다.
클로저는 외부에서 내부함수로 접근해 데이터를 사용하는 것이다. 그냥 테스트 해보았다.
