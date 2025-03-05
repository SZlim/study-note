
###### 순서
- HTML작성한 다음 HTML의 element를 가져와 javaScript로 작업한다.
#### input Values
- 😁tip: input과 button을 많이 사용할 경우, HTML에서 div안에 넣어, class로 만들자.
- 😁console.dir()를 통해  input의 property를 찾아 볼 수 있다.
- 😍HTML에서 element에 id를 부여한 경우, ==document.queryselector()에서 반드시"# + id명"을 입력해야, 해당 id를 javascript가 찾을 수 있다.==(반드시 '#'을 해야한다.)
	- 단, .getElementById()는 id를 추적하기때문에 id명만 정확히 넣어주면 됨.
- const로 선언된 HTML element(.document)를 통해 좀 더 정밀한 조사가 가능하다. ==해당 선언된 const안에서 queryselector()를 통해 범위를 좁혀 원하는 목표를 찾을 수 있다.==
- value - input에 입력된 value를 확인할 수 있다.
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