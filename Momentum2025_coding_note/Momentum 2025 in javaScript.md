
###### 순서
- HTML작성한 다음 HTML의 element를 가져와 javaScript로 작업한다.

### Login part

- input Values
- 😁tip: input과 button을 많이 사용할 경우, HTML에서 div안에 넣어, class로 만들자.
- 😁console.dir()를 통해  input의 property를 찾아 볼 수 있다.
- 😍HTML에서 element에 id를 부여한 경우, ==document.queryselector()에서 반드시"# + id명"을 입력해야, 해당 id를 javascript가 찾을 수 있다.==(반드시 '#'을 해야한다.)
	- 단, .getElementById()는 id를 추적하기때문에 id명만 정확히 넣어주면 됨.
- const로 선언된 HTML element(.document)를 통해 좀 더 정밀한 조사가 가능하다. ==해당 선언된 const안에서 queryselector()를 통해 범위를 좁혀 원하는 목표를 찾을 수 있다.==
- 😍==value== - input에 입력된 value를 확인할 수 있다.
- username 길이 제한 방법
	- string의 길이를 구하는 방법은 .length로 구할 수 있고 등호를 통해 제한할 수 있다.
	- ex) username.length >15
- 단, 선호하는 방법은 아님 이유는..
	- 항상 user를 믿지 말아야 함
	- 항상 최고의 툴을 사용해야 함.
	- 이미 브라우저가 가지고 있는 기능을 사용하는 것을 추천
- HTML의 input자체적 기능을 사용할 것을 권장
	- required
	- maxlength
	- 😎HTML 내 input의 유효성을 검사하기 위해서는 form안에 input이 존재해야 함.
		- 단, form안에 input을 넣을 경우, 엔터를 입력할 때마다 form은 자동적으로 submit이 된다.(새로고침)
		- ==form이 submit(새로고침)이 되는 것을 막아줘야 한다.==
	- submit도 eventlistener로 감지할 수 있다.
		- 😁submit 역시, 엔터를 누르거나 버튼을 클릭할때 발생한다.
		- form이 submit되고 브라우저가 새로고침하는 것은 브라우저의 기본동작이기 때문에, 기본 동작이 발생하지 않도록 해야함.
		- ==eventlistener를 활용할때는 function을 바로 실행시키려고 하는 것이 아니다.==
		- 또, addEventListener안에 있는 함수는 우리가 직접 실행하지 않는다.
			- 브라우저가 실행해줌.
			- event에 대한 정보도 담아줌.
	- ==😎preventDefault() - form이 submit되는 기본 동작을 막기 위한 함수.==
		- preventDefault 함수는 EventListener 함수의 '첫 번째 argument' 안에 있는 함수이다. 첫 arument는 지금 막 벌어진 event들에 대한 정보를 갖고 있다.  
		- JS는(기본적으로)argument를 담아서 함수를 호출하는데, 이 argument가 기본 정보들을 제공하고 있다. 
		- ex) 누가 submit주체인지, 몇 시에 submit을 했는지 등등 콘솔에 출력해보면 알 수 있음
		- 😎form에서 발생한 submit event 관련 정보를 담을 용도로 onLoginSubmit 함수에 event라는 매개변수를 추가(관용적으로 event라고 사용. event는 정보를 담는 object) - event는 해당 함수의 eventListener함수의 첫번째 인자(arguement)로 주어진다., 우리는 공간만 만들고 받기만 하면됨.
		- ex) function onLoginSubmit(event) {event.preventDefault();}
	- event로부터 얻을 수 있는 다양한 정보가 존재함. 포인터 위치 등등 또, 다양한 event가 존재함.
- Getting username
	- user접속 후 (이름 제출 후), log in 시, form을 사라지게..
		- ==CSS에 .hidden classname생성== => CSS를 통해 form을 숨긴다.
			- hidden은 display:none;
		- HTML에 h1을 추가, hidden으로 classname부여.
			- 해당 class는 요소를 숨기는 역할을 함(form을 숨김.)
			- h1요소는 존재하지만 숨겨져 있음.
		- classList.add()/.remove()로 classname을 추가/삭제해 form을 숨겨준다.
		- 😭즉, loginForm에 form과 h1 모두의 속성을 부여 후, 원하는 value(username)를 얻었을 때, form을 h1의 hidden class 작동, form을 숨기고(.add), h1에서는 hidden을 삭제(.remove)해 string을 화면에 표시함. 코드참고[[JavaScript 예제모음#예제4(getting username)]]
	- ==string조합==
		- "hello " + username - 방법1
		- ==`hello ${username}` - 방법2($``$(백틱)안에 추가)==
			- $``$(백틱)안에 string과 변수를 넣어 원하는 문구 출력 - 선호하는 방식
				- 규칙1 - ${변수명}으로 string과 결함
				- 규칙2 - ==반드시 $``$(백틱)으로 시작해야 함.==
- Saving username
	- localStorage (이미 브라우저에 존재함.), key와 value가 필요.
		- 😎value저장 방법 - 자주 사용되는 방법, 가장 쉬운 방법
		- .setItem - localStorage에 정보 저장
		- .getItem - localStorage의 정보 호출
		- .removeItem - localStorage의 정보 삭제
- Loading username
	- localStorage에 유저의 정보가 있을 경우 form을 보여주지 않고 h1을 보여주기 위한 코드 작성
		- 유저정보가 없을 경우 form 
		- 유저정보가 있을 경우 h1
	- localStorage의 유저정보 확인법
		- .getItem으로 유저정보 확인 가능
		- ==유저정보가 없을 경우 null을 반환한다.==
	- 😎조건문 완성을 위해, form과 h1모드 class = hidden으로 부여해, 숨겨주고 시작한다.
	- localStorage에서 전달되는 username과, loginInput에서 전달되는 username은 다른 인자이다.
		- 죽, paintGreeting함수의 username(localStorage로 부터), onLoginSubmit의 username(loginInput으로 부터)이 인자가 다름. 구분이 필요할 경우 구분해야 헷갈리지 않는다.


### Clock part

#### intervals
- clock을 만들기 위해서는 html에 h2를 생성, default값으로 00:00부여한다.
- intervals - 매번 일어나는 무엇인가를 뜻함.
	- 😎==setInterval()== - 특정 시간마다 어떤 함수의 호출을 실행함.
		- javaScript에 내장되어 있음
		- 두개의 argument를 받음
			- 첫번째, 실행하고자 하는 function
			- 두번째, 호출되는 function의 간격, ms(milliseconds)
#### Timeouts and Dates
- ==setTimeout()== - 어떤 함수를 특정 시간 내 1번만 호출
	- 두개의 aurgument를 받음
		- 첫번째, 실행하고자 하는 function
		- 두번째, 호출되는 function의 간격, ms(milliseconds)
- ==Date()==
	- ==new Date()== - 현재 날짜 및 시간 정보 생성, 동적인 시간을 표시(매번 최신 시간정보를 얻을 수 있음.)
		- javaScript에 기본 기능
	- date.getHours()
	- date.getMinutes()
	- date.getSeconds()
	- 매 초마다 하고 있는 것은 날짜,시간,분, 초에 대한 정보를 가진 object를 매 초마다 생산하는 것.
		- 이 반복작업이 시계처럼 보이게 하는 것.
- 새로 고침 후 시간이 바로 보여지지 않음, 1초 후 생성
	- 문제해결
		- 😍시간함수 getClock()을 website가 load되자마자 즉시 실행하게 하고, interval을 실행
		- 즉시 실행되기 때문에 1초 기다림이 없어진다.
- 시계 화면 표시
	- 😍innerText로 h2#clock에 표시
	- ==innerText== - HTML 내부 텍스트 콘텐츠를 가져오거나 설정하는데 사용되는 속성,

#### padStart
- ==padStar()==는 ==string에 사용할 수 있는 function.==
- padStar는 기존 string을 보다 길게 만들어야 할때 사용.
	- 앞에 원하는 길이만큼 특정 글자를 채움.
- 😍padStart()는 number 함수 안에는 사용할 수 없다.
	- 즉, number를 text로 변경해야 한다.
	- ==String()으로 감싸면 number가 string으로 변한다.==
	- 사용법
		- ex) "1".padStart(2, "0")
		- 길이가 1인 문자를 문자열의 길이가 2가 되도록 해주고 "0"으로 앞을 채워줘라.
		- 이미 길이가 2인 문자에서는 작동하지 않음.
- padEnd(), padStrar()와 반대 개념
	- padEnd는 기존 string을 보다 길게 만들어야 할때 사용.
	- 뒤에 원하는 길이만큼 특정 글자를 채움.



---
#### Tip
- 😍==string만 포함된 변수는 대문자로 변수명 표시==, string을 저장하고 싶을때 사용.(중요한 정보를 포함하지 않음.)
- 😍==반복되는 string을 const로 고정시켜야 오류가 줄어듬(변수)==
	- ==대문자 변수로 저장==, string이라는 사실을 기억하고 상기하기 좋음.
	- string작성을 줄여야 생각하지 못한 오류도 줄어든다.
- 반복되는 코드는 function으로 만들어 두면 편리하다.
- 😎==특정 함수를 연결할때 $``$(백틱)을 사용해 연결한다==.
	- ex) '`${a}:${b}`'