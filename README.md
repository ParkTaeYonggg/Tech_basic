# Tech_basic
## this
쉽게 생각해 this는 this를 불러낸 함수를 나타낸다.


<img width="300" alt="스크린샷 2021-12-13 오후 5 37 18" src="https://user-images.githubusercontent.com/86910922/145778924-cb246471-f1dd-4e90-a3aa-073dfd16942e.png">
<img width="300" alt="스크린샷 2021-12-13 오후 5 37 12" src="https://user-images.githubusercontent.com/86910922/145778932-b7e65f0d-0179-47ec-93b7-02fa643fde49.png">

위처럼 fn1에서의 메서드는 this를 찍어보면 자신을 불러낸 함수를 쳐다보고 있다. <br>
그치만 fn2는 fn1에 있긴 하지만 따로 만들어지고 불려진 존재이다.<br>
따로 만들어진 fn2는 당연히 fn1을 감싸는 함수 내에서 실행된 것이니 fn1을 감싸는 함수를 바라볼 것이다.


<img width="400" alt="스크린샷 2022-01-22 오후 11 31 53" src="https://user-images.githubusercontent.com/86910922/150642769-cb672b51-1db9-4d2e-92c0-d08bc684add4.png"><img width="400" alt="스크린샷 2022-01-22 오후 11 31 36" src="https://user-images.githubusercontent.com/86910922/150642777-2b2e9926-6270-4422-8a7a-673c39cdd440.png">

리액트에서는 작동방식이 좀 다르다. bind로 묶어줘야 한다. -> 바인드로 묶인 함수를 바라본다.
자바크스립트에서라면 
- 언디파인 자리가 버튼1을 가리킬 것이다.
- 바인드로 묶지 않았다면 ii나 iii는 윈도우를 가리킬 것이다.
- 바인드로 묶지 않고 thisFn에서 직접 inner함수를 불러오면 this는 그 함수를 호출시킨 thisFn을 바라볼 것이다.

클로저는 외부에서 내부함수로 접근해 데이터를 사용하는 것이다. 그냥 테스트 해보았다.

## promise
프로미스는 비동기 처리방식이다.<br>
-> 프로미스 함수의 작동방식은 프로미스가 내장된 함수 실행 -> 비동기 실행되는 동안 대기상태 돌입 -> then으로 다음 액션 실행-> 반복됨.
--> then으로 연결된 함수들은 전부 공통된 값을 공유함.
---> then으로 연결된 함수에는 일반함수가 들어가도 됨. => 일반함수에서 변경된 값을 리턴받으면 변경된 값으로 다음 then이 실행됨.
-----> 모두 프로미스 객체가 리턴 되는 것임.

<img width="300" alt="스크린샷 2022-01-22 오후 5 16 22" src="https://user-images.githubusercontent.com/86910922/150630652-54ce07af-db51-4f05-9226-2cca8b0d8ca9.png"><img width="300" alt="스크린샷 2022-01-22 오후 5 16 14" src="https://user-images.githubusercontent.com/86910922/150630658-7f0225c2-fe35-4b47-a776-d0c37a28362e.png"><img width="300" alt="스크린샷 2022-01-22 오후 5 16 01" src="https://user-images.githubusercontent.com/86910922/150630666-bb857fa6-b624-4764-bcf8-5bef69485ed4.png">

-------> 문제점은 분기처리도 어렵고 중간에 에러나면 어디서 난지 알 수 없다.

## async/ await

어싱크 어웨잇은 프로미스의 업그레이드 버전이다.
함수를 async로 감싸면 비동기 처리가 되고 await처리로 프로미스 함수 값을 변환해준다.

<img width="400" alt="스크린샷 2022-01-22 오후 7 07 05" src="https://user-images.githubusercontent.com/86910922/150634395-2cd0a591-2ae8-45f1-a5de-0c1e87506c61.png"><img width="400" alt="스크린샷 2022-01-22 오후 7 07 15" src="https://user-images.githubusercontent.com/86910922/150634397-18324160-946e-4e7d-a714-cb826ec27652.png">

위처럼 프로미스 객체가 아니면 await에 ...이 붙는 것을 알 수 있다.


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

## fetch vs axios
- fetch 
  ㄱ. 외부에서 가져올 필요가 없음. -> 자바스크립트 자체 지원
  ㄴ. 브라우저 대응에 약함 -> 옛날 브라우저는 지원이 안되는 경우가 있음.
  ㄷ. json형태로 변형이 필요함.
  ㄹ. 라이브러리 업데이트에 대응이 강함 -> 리액트네이티브 같이 업데이트가 잦은 라이브러리에서도 자바스크립트 자체 지원이기 때문에 바로 사용이 됨.
- axios 
  ㄱ. 외부에서 가져와야 함. -> import해서 사용함.
  ㄴ. 브라우저 대응에 강함 -> 옛날 브라우저도 지원해줌.
  ㄷ. json형태로 자동변형해줌.
  ㄹ. 라이브러리 업데이트에 대응이 약함 -> 사용하는 라이브러리가 업데이트 되었을 경우 사용이 안되는 경우가 있음.


## web-server vs web-application-server
- web (대표 : 아파치)
  ㄱ. http 프로토콜 통신만 받고 정적인 처리를 담당하기에 적합하다. 
  (이미지, 텍스트, 동영상, 자바스크립트 등 즉시응답 가능한 것들)
- was (대표 : 톰캣)
  ㄱ. 비즈니스로직(데이터베이스나 유저 인터페이스쪽 사이의 정보를 전달해주는 곳으로 웹컨테이너라는 다른 이름도 있다함-> xml요청을 메모리에 담아서 -> 디비를 들려 데이터를 가지고 -> 다시 처리할 거 하고 웹서버로 전달함)을 처리하여 다이나믹한 컨텐츠를 전달함. 
