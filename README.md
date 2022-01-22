# Tech_basic
## this
쉽게 생각해 this는 this를 불러낸 함수를 나타낸다.


<img width="300" alt="스크린샷 2021-12-13 오후 5 37 18" src="https://user-images.githubusercontent.com/86910922/145778924-cb246471-f1dd-4e90-a3aa-073dfd16942e.png">
<img width="300" alt="스크린샷 2021-12-13 오후 5 37 12" src="https://user-images.githubusercontent.com/86910922/145778932-b7e65f0d-0179-47ec-93b7-02fa643fde49.png">

위처럼 fn1에서의 메서드는 this를 찍어보면 자신을 불러낸 함수를 쳐다보고 있다. <br>
그치만 fn2는 fn1에 있긴 하지만 따로 만들어지고 불려진 존재이다.<br>
따로 만들어진 fn2는 당연히 fn1을 감싸는 함수 내에서 실행된 것이니 fn1을 감싸는 함수를 바라볼 것이다.
클로저는 외부에서 내부함수로 접근해 데이터를 사용하는 것이다. 그냥 테스트 해보았다.

## promise
프로미스는 비동기 처리방식이다.<br>
프로미스, 어싱크어웨잇 두가지가 존재하는데 저것들이 걸려 있으면 비동기 처리에도 순서가 적용되어 나름 체계적으로 활용할 수 있게 된다.

## arrow function
화살표함수는 자신에게 바인딩하지 않는다.<br>
즉, 상위 객체를 나타낸다. 항상.<br>
그리고 코드가 간략해져서 사용하는데 편리한 것도 있다.

## module
모듈은 리액트 파일을 이루는 모든 것 (css, html, javascript ...etc)을 이야기 한다.

## module bundler = webpack
웹팩은 모듈을 하나로 모아주고 화면에 뿌려주는 역할을 한다. 크게 4가지로 구성되어 있다.
1. entry : 입구다. 파일을 하나로 묶어주는 부분
2. output : 묶은 파일 결과물들을 보여줄 곳이다.
3. loader : 자바스크립트와 JSON만을 읽을 수 있는 웹팩에게 다른 자원도 읽을 수 있도록 도와준다. 예를들어 css, html, image등등
4. plugin : 최종적으로 loader를 통해 들어온 것을 웹팩에 어울리는 형태로 변환시켜 주는 것이다.

## babel
바벨은 se6문법을 se5문법으로 형태를 변환시켜 주는 것이다.

###그래서 결국 왜 웹팩과 바벨이 필요한가?
이유는 개별적으로 모듈을 적용하면 사용처에서도 무거울 것이다. 이를 덜어주기 위해 하나의 결합물로 만들어주기 때문에 웹팩과 바벨이 중요한 것이다.

## Template Literal
템플릿 리터럴은 "", '' 가 아닌 ₩₩ 백틱을 사용한다. 이것의 특징은 변수 사용을 허용해주거나 조건, 반복문 등을 허용시켜준다.

## defalut parameter
디폴트 파라미터라는 것은 매개변수로 흘러 들어온 값이 정의되지 않았다면 자동으로 할당시켜주는 값을 말한다.<br>
const test = (temp = "방가방가") {console.log(temp)};<br>
test(); //<<< 이때 출력물 : 방가방가<br>
test("매우방가"); // <<< 이때 출력물 : 매우방가<br>

## useMemo
유즈메모는 인자값을 부여받은 데이터가 변화되었을 때에만 함수 내부에 작성된 값이 랜더되게 된다.

## 쿠키 세션 캐시
쿠키 : 쿠키는 개인이 가지고 있는 정보다.
-> 어디 홈페이지 들러서 어떤 활동을 했건 입력을 했건 남게 되는 기록들이다.
--> 근데 정보를 가지고 다른 홈페이지 들러서 또 활동을 한다면 그쪽에서도 확인할 수 있을듯 해서 보안상 문제가 있어 보인다.

세션 : 세션은 페이지 관리자가 가지고 있다.
-> 관리자가 담당하니까 보안에 좀 더 강한 것이다. 회원 정보라던가 검색어가 될 수도 있고 민감한 거 가지고 있다고 보면 된다.
--> 보안에는 좋지만 데이터가 많아지면 홈페이지가 무거워진다고 한다는데 이해가 된다. 수십만명의 사람 정보를 가지고 있으면 무거울 수밖에 없는듯 하다.

캐시 : 캐시는 장바구니 같은 임시 보관소다.
-> 사용자가 서버에 들러서 데이터를 가져와 페이지를 화면에 보여줬다. 잠시 다른 페이지를 갔다가 다시 돌아왔을 때 임시 보관된 데이터가 없다면 같은 데이터를 또 가져와야 할 것이다. 이런 문제점을 잠시 가지고 있음으로 해결해 줄 수 있는 것이다.

## forEach vs map vs reduce
-> 포이치는 리턴값을 가질 수 없다. 포이치문 안에서 할당을 시키는 것은 가능하지만 밖으로 내보내 바로 사용하는 것은 안된다.
-> 맵은 리턴값을 가질 수 있다. 리턴 시 새로운 배열을 만들어 외부로 반환해주기 때문에 바로 사용이 가능하다.
-> 리듀스는 리턴값을 가질 수 있다. 리턴 시 배열의 형태가 아닌 최종 값을 내보내준다.(아래 사진 중 15라는 값이 그 리턴 값이다.)

<img width="300" alt="스크린샷 2022-01-22 오후 4 01 26" src="https://user-images.githubusercontent.com/86910922/150628591-f55c3cae-f830-4b5f-9ff8-56c1e6c55ad4.png"><img width="300" alt="스크린샷 2022-01-22 오후 4 02 26" src="https://user-images.githubusercontent.com/86910922/150628628-e41263ea-3f5e-493b-975d-4dd032dcc67e.png">



