###### [[HTML 입문(문법등 참고용)]] 

- javascript는 이미 웹브라우저에 설치되어 있다.
- js코드와 css코드를 ==웹에서 실행하기 위해선 html이 필요==하다.(접착제역할)
- javascript는 사용자와의 상호작용을 위해 만들어 졌다.
## ==Javascript기본문법==
- js파일은 주로 끝에서 작성한다.(위에서 부터 가져오지 않는다.), script src로 가져온다(클로징필요)
- console.log() - 브라우저에 프린트, 파이썬의 "print"
- const - 변수. 변수값 update 불가.
- let - 변수, const와 동일. 단, 변수값 update가능.

#### ==Basic data types== 
- integer(정수)+float(소수)
- text(문자)
	- 2와 "2"는 다르다. 2는 integer, "2"는 string.

#### ==Variables(변수)==
- 값을 저장하거나 유지하는 역할
- const: js에서 변수 선언 방법(constant:상수, 바뀌지 않고 계속 유지됨을 의미함.)
- ==😍const는 변수 값은 업데이트할 수 없다.==
- const에는 단어 공백이 존재할 수 없다.
	- 단어 공백이 필요하다면 대문자 사용. "camelCase"라고 부름(js식 규칙)
		- ex) const myNameIsSeoungjin();
			참고 - 파이썬은 언더바로 공백을 표시함."snake_case"라고 부름, 파이썬은 const가 필요없다.
- ==let==: const와 동일한 변수. 단, ==변수 값을 업데이트할 수 있다.==
- 중요: 항상 const를 사용하되, 필요시(변수값 업데이트가 필요할 경우),let을 사용. ==절대 var는 사용하지 않는다.==

#### ==boolean==
- true
- false
- null(비어있음을 뜻함) - 변수에 할당되는 값. 변수가 값이 없음을 명확히 할 때, 사용
- undefined(변수에 값을 부여하지 않은 상태), null과는 개념이 다르다.

#### ==array==
- 변수 뒤 [](리스트)를 만들고 작성, ","로 구분한다. array안에는 유효한 데이터 타입이나, variable이 들어갈 수 있다.
- 원할 경우, array 내 item에 접근할 수 있다.
	- ex) console.log(toBuy[2]);
- 필요한 경우, array 내 item을 수정할 수 있다.
	- ex) toBuy[2] = "water"; => toBuy의 2번 인덱스 값을 재설정
- array는 push를 통해 item을 추가할 수 있다.
	- ex) toBuy.push("corn"); => 기존 item 뒤에 추가로 배치.

#### ==object==(생성된 object는 javascript와 비슷한 모양을 하고 있다.)
- 생성방법 => ex) const player = { name: "seoungjin", age: 83,};으로 object를 생성할 수 있다.
- object 내 각각의 element를 가져올 수 있고, array와 동일하게 object내 인덱스 값을 가져와 변경할 수 있다.
	- ex) player==.name== = "Seoungjin Lim";
- object생성 후 object안에 새로운 item을 만드는 것도 가능.
	- ex) player==.sexy== = =="soon"==, };

#### ==function==(함수, 어떤 코드를 캡슐화하여, 계속 사용하는 것)
- 작성법: ex) ==function plus()== { console.log(2+2); }
- ==실행법: ex) plus();== , ()는 실행한다는 뜻.
- 👍 function안에 data를 넣어두는 것 보다, function 밖에서 data를 넣을 수 있게 하는 것이 훨씬 유용함.(여러가지 일을 같은 코드로 하기 위함.)
- ==function안에서 data를 받는 방법은, ()안에 무언가를 작성하는 것.==
	- ex) function plus(a, b){ console.log(a + b);}
		plus(5, 10); => plus()에서 값을 보낼때, a, b는 placeHolder역할을 함. ==반드시, 순서를 지켜야 한다==.(각 placeHolder에 맞는 순서를 이야기 함.)
- 하나의 data만도 받을 수 있다.(?)
	- ex) function minusFive(a){ console.log(a-5);}
		minusFive(5, 100, 200,300, 400); =>값은 0, 즉 아주 많은 argument를 보내도(요청하는 쪽), 문제가 되지 않는다.(예제의 function은 많은 argument를 받을 준비가 되지 않았기 때문.)
- function의 정의는 <u>function의 body({}로 둘러진 부분)안에서만 사용할 수 있다.</u>
		ex) function plus(a){body} => a는 function의 밖에서 정의되지 않았기 때문에.. undefined
- ==심화==
	- ex) const calcurator ={ plus: fucntion(a+b){console.log(a+b);},} => object생성 후, function 정의해 사용할 수 있다.
- ==function은 내부 --> 밖 순으로 실행된다.(2가지 함수가 함께 사용된 경우.)==

#### ==return==(헷갈림.)
- consloe.log()를 사용하지 않을 것을 전제함. => ==function밖에서 결과값을 얻기 위함.==
- console.log()없이, 결과값에 닿을 수 있다.(function에서 무엇인가를 return하기 때문에,,)
- function안에서 return을 하면, function을 실행할때 마다, function의 정의한 부분을 대체한다.
	- ex)const age = 83;
		function calculateKrAge(ageOfForeigner){ _return_ ==ageOfForeigner + 2==; }
		const krAge = ==calculateKrAge(age)==;
- 어떤 작업을 처리하고 그 결과를 return하기 위해 function을 사용하는 것이다.(console에 출력하려고 function을 사용하는 것과는 다름.)
- <u>작업 결과가 필요하지 않은 fucntion은 return이 필요없다.</u>
- ==return을 하면 function은 작동을 멈추고 결과값을 return후 끝내버림.==

#### ==conditionals==(조건문)   
- 조건문은 boolean으로 판별이 가능하다.== true or false.
- if -  조건이 true 일때,
	- ex) if(){}
- else - if, else if의 ==조건이 false일 경우 작동.== 위 조건이 true일 경우 작동하지 않음. else는 선택적 사항임.
	- ex) if(){} else{}
- ==else if== - if가 false일때, 한가지 condition(조건)을 더 사용하게 해줌. (<u>코드 실행 순서를 잘 생각해야 함.</u>작동하지 않을 수도 있기 때문..)
- ==동시에 두가지 condition을 확인할 수도 있다.== 조건을 연결해줄 연산자가 필요함.
- 많은 condition(조건)을 연결할 수 있다.

- 연산자
	- ==AND 연산자 - &&기호로 표시,== ==두 조건이 모두 true여야== 함을 javascript에 전달.  ==두 조건 모두 true일 경우,true. ==하나라도 flase일 경우, 결과도 false.
	- ==OR 연산자 - ||기호로 표시, 두 조건 중 하나만 true인지== 확인해 javascript에 전달. ==하나의 조건만 true이면 결과는 true.== 단, 🤩==두 조건 모두 false인 경우만, false.==
	- ==EQUAL 연산자== - === 기호로 표시, 1개의 =(부등호)는 value를 할당,
	- ==불일치 연산자== - !== 기호로 표시,

## Javascript on the browser

document에서 항목을 가져온다.
documnet 항목들을 변경한다.

#### The document Object
- javascript를 사용하는 이유, HTML과 상호작용을 위함.
	- HTML을 Javascript에서 읽어올수 있어야 함.
- ==즉, HTML의 element를 javascript를 통해 읽고, 변경할 수도 있다.==
	- javascript는 HTML element를 가져오지만, HTML자체를 보여주지는 않음(object를 보여줌.)
- console에서 <u>console.dir(document)를 실행하면 document(javascript관점)으로 HTML을 보여준다.</u>
	- 즉, HTML의 title을 javascript로 가져올 수 있다.
		- document.title
- <u>HTML과 javascript를 연결하기 위한 모든 설정은 이미 준비되어 있음.</u>(이미 연결됨.)
	- 무수히 많은 기능들이 이미 준비됨.

#### HTML in javaScript
- HTML의 id를 가진 tag를 console에서 가져오는 방법
	- document.getElementById(), vscode에서 저장 후 브라우저를 새로고침해야 적용됨.
- 상호, 어떻게 작동하는지 명확히 이해하는 것이 중요하다.

#### Searching for Elements
- HTML에 정의된 id는 JavaScript에서도 같아야 함.






#### ==주요function==
- promft() - fucntion(함수)은 오래된 javascript의 기능이다. (비추천)
		지금은 html과 css로 대체됨.
- ==isNaN()== - ==variable이 NaN인지 알려줌==. 해당 function에 하나의 argument를 주면, ==boolean으로 반환(return)==한다. 
- ==parseInt()== - ==string을 number로 바꿔준다==. ==숫자와 숫자가 아닌 것을 구별 해 준다.==(NaN인지 확인가능)
	string일 경우, 숫자와 크기를 비교할 수 없다.
- typeOf - variable의 type을 알려줌.(string, number..)
	- ex) console.log(typeOf age);






#### ==기타상식==
- NaN - Not a Number
- null(비어있음을 뜻함) - 변수에 할당되는 값. 변수가 값이 없음을 명확히 할 때, 사용
- undefined(변수에 값을 부여하지 않은 상태), null과는 개념이 다르다.

#### ==숏컷==
- ! - html문서양식 작성
- link:css - html에 css문서 링크 자동 생성