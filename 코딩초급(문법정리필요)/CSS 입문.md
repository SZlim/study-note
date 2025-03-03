Cascading style sheet의 약자,
cascade 뜻처럼, 브라우저가 CSS코드를 읽을 때, ==위에 있는 코드부터 차례차례 읽는다.==
	가장 마지막 변경한 코드가 실행 된다. 즉, 코드순서가 결과에 영향을 준다.
	==모든 코드를 처음부터 다시 쓸 필요가 없는 것.==
CSS는 웹사이트의 Contents가 어떻게 보여야 하는지 Browser에 알려준다. 
※ 모든 속성을 외울 필요가 없다. 필요시 검색
==CSS의 역할, HTML 태그를 가리키는 일==
※ 각 id는 각 element에 #과 id이름을 결합해 속성을 부여할 수 있다.
	ex) #tomato 은 id=tomato와 같은 뜻이다.
※ 요소를 가르키는 방법은 tag와 id(#), 두 가지 이다.
※ CSS 작성 중 * 표시는 모든 것을 뜻 한다.
※ 크기단위 중 vh는 viewport height다.
==selector 3가지==
	body
	. = 클래스
	# = id

CSS작성법
	selector(가리키는 대상) + {원하는 속성 작성}
	ex) h1{
	 color: blue;
	}
	==위의 문법을 반드시 따라야 한다.==
	각 속성에 맞는 값을 써야 브라우저에서 작동한다.


css파일을 HTML에 추가 하는 방법
	- 같은 HTML코드에 CSS코드를 같이 작성(비추천), ==inline CSS 라고 함==
		- style 태그를 이용해 HTML문서에 작성
	- **HTML과 CSS 코드를 분리 작성(추천), ==external CSS 라고 함==
		- <link href ="" rel="stylesheet" /> 로 따로 작성한 css파일을 불러온다.
		- 여러 HTML에 위 코드를 통해 동일한 CSS적용이 가능하다.


==Block== - div(박스)와,P(파라그래프) 등 과 같이 옆에 ==다른 요소가 올 수 없는것==
	특징, 
	대부분이 block이다.
		각 div(박스)는 id를 부여해 구분할 수 있다.
		==각 div의 id는 #과 id 를 결합해 속성을 부여할 수 있다.==
		==margin== - box의 border(경계)의 바깥의 공간
			방향을 입력(ex margin-top: 20px;)해 각 방향 별로 공간크기 설정 가능
			방향 값을 일일이 지정해 주는 것은 힘든 일.
			다른 방법으로, ===margin: 20px 15px; 로 상하 20px, 좌우 15px을 지정할 수 있다.==
			1개의 값은 사면, 2개의 값은 상하/좌우, 4개의 값은 상하좌우 설정 가능.
				4개의 값 순서 - 위/오른쪽/아래/왼쪽 순
		==collapsing margin 현상== - _어떤 박스의 경계가 다른 박스의 경계와 같은 경우_, 두 margin은 1개로 취급된다. ==상하만 적용== (_더 깊이 있게 알려고 하지 말고 이해하고 대안을 찾아야 한다._)
		==padding== - box의 border(경계) 안쪽의 공간
		border - box의 경계, 여러 border의 속성이 있지만, 대부분 한 종류만 사용.(안예쁨)
			border: 2px solid color(지정); 해 사용한다.
			사용방법 - border: size lin-type color;
	
==inline ==- block과 반대 개념, ==다른 요소가 올 수 있다.==
	span, a, image 등..
	※ ==inline요소는 높이와 너비를 가질 수 없다.==
		위/아래 margin 값을 가지고 싶다면, inline을 block으로 변경해야 한다.
※ ==display:== 를 이용해 ==inline을 block으로 block을 inline으로== 변경 할 수 있다.

class - 원하는 요소를 가리키면서도 겹쳐도 되는 유용한 방법
	※ __class명은 유일할 필요가 없다.__=/ id와 반대개념(여러 요소를 같이 사용 가능.)
		ex) class = tomato potato watermelon 여러 개의 요소입력 가능
	==.은 class명이라는 뜻==
		ex) .tomato 은 class=toamto와 같다.
	기존의 복잡한 id요소를 class로 변환.
	style에서 .class이름으로 정의해 사용

===inlien block== - div는 기본적으로 block이다.(inline은 브라우저가 인식을 못한다.)
	inline-block은 block으로 인식,,==높이와 너비, full-margin을 가질 수 있고, 다른 요소가 옆에 올 수 있다.==(div는 다론 요소가 옆에 올 수 없다.)
		단점: 요소사이에 빈 공간 존재
			정해진 형식이 존재하지 않음.
			※ Responsive Design(반응형 디자인)을 지원하지 않음
	inline-block은 잘 사용하지 않는다.(아마, block, inline도 잘 사용하지 않을 듯..)

==flexbox== 2d레이아웃, 박스 배열에 유용함
	규칙
	- 자식 엘리먼트에는 어떤 것도 적지 말아야 함
		- 부모에게 ==display:flex;==로 작성/실행
		- 이후, justify-content:로 div(자식)의 위치 수정
			- ex) <body> - 부모 엘리먼트
					<div></div> - 자식 엘레먼트, flexbox에 관한 것을 적지 말아야함
					</body>
	- ==justify-content==는 main axis(주축)에 적용됨(디폴트 값: 주축)
	- ==aline-items==는 cross axis(교차축)에 적용됨(디폴트 값: 수직)
	※ 부모인 body가 height를 가지고 있지 않으면 aline-items는 적용되지 않는다.
		(이미 body의 중심을 차지 하고 있으므로..)
	-==내용이 있는 div(자식)은 flex container가 될 수있다.==
	-만약, 자식의 display:flex;를 삭제할 경우 작동 중지, ==부모 엘리먼트가 flex를 가지고 있어도 작동하지 않음.==

==flex-direction== 주축과 교차축을 바꿀 수 있게 해줌 (디폴트: row)
	==column== 주축이 수직, 교차축이 수평이된다.(flexbox의 반대)
		flex-direction 값이 column일 경우, aline-items는 main axis(주축)으로 움직인다.(justify-content는 교차축으로 움직임)
	row 디폴트 값
	column-reverse
	row-reverse
flex-wrap
	nowrap
	 flexbox는 자식인 div의 width가 있더라도 화면 크기에 따라 모든 요소를 같은 줄에 있게 만들 수 있다.
	wrap
		wrap을 적용할 경우 자식div의 width가 유지된 상태로 box가 움직임
	wrap-reverse 거의 사용하지 않음.
position 위치를 조금 이동하고 싶을 때 사용.
	position:fixed;
		- top/bottom/left 등의 속성을 통해 block, margin이든 관계없이 해당 객체는 다른 객체 위에 고정된다.(==레이어가 달라짐)==
		- ==fixed== 사용하면 레이어를 부수고 다른 레이어로 위치함. ==**가장 위에 존재하게 됨!!==
	position:static; (디폴트 값)
		레이아웃이 박스를 처음 위치하는 곳에 두는 것을 뜻함.
	==position:relative;== 엘레먼트가 처음 위치한 곳을 기준으로 수정함.
		top/right/bottom/left의 속성을 사용가능
	==position:absolute;== 가장 가까운 relative 부모를 기준으로 이동
		ex) ==div가 relative가 아닌 경우 body를 기준으로 이동==. 이때 div를 relative로 할 경우, div를 기준으로 이동함.
		- top/right/bottom/left의 속성을 사용가능
peseudo seletors 좀 더 세부적으로 element를 선택하게 해주는 것
	Tag이름+:+{}로 사용함 
	ex) div:lastchild{} (마지막 객체에 적용)
		-first-child
		-last-child
		-nth-child(숫자)를 사용, 중간 객체 선택
		-nth-child(even), 여러 객체 내에서 짝수 개체 선택
		※ even(짝수), odd(홀수)
		-nth-child(숫자+n) 몇 번째 부터 속성을 적용할지 선택할 때 사용.
	==id나 class를 만드는 것 보다 훨씬 유용한 방법==
	==::placeholder 는 placehorder를 스타일 할수 있게 해준다. ex)input::placehorder{}==
	::selection 개성있는 웹사이트를 만들 수 있게 해준다.
		ex)p:selection{} 를 통해 문장을 드레그 선택할 때의 색 변경을 해준다.
	::first-letter 문장의 첫 글자를 스타일 할 수 있게 해준다.
	
combinators(결합자)
	father selector 작성 후 child selector작성으로 속성 적용
	ex) p span{ color: tomato;}
	- ==div span== 부모에 속한 자식
	- ==div > span== 은 div의 바로 밑 span(자식)
		direct children(자식)
	- ==div + span== 은 div 다음의 span에 속성 적용(_꼭 다음에 오지 않아도 형제다._)
		next to sibling(형제)
	-div ~ span 은 div 바로 다음에 span이 오지 않을 때 사용	
	개념의 이해가 중요.
required/optional(복습필요), form/input과 관련
==attribute selector== 어떤 것이든 선택하게 해준다.참고: [MDN](https://developer.mozilla.org/ko/docs/Web/CSS/Attribute_selectors)
	- 사용법: tag[attribute="value"] 스타일적용
	- 사용법: ==tag[attribute~="value"]== vlaue를 포함하는 모든 tag에 스타일 적용
		- ~=는 특정 단어를 contain(포함)을 의미한다.
		- $=는 접미사로 value가 값에 포함된 경우 요소 선택
		- ^=는 접두사로 value가 값에 포함된 경우 요소 선택
	ex) input[type="password"], type이 password인 input들에게 속성을 부여
	ex) input[type~="password"],password를 포함하는 모든 tag에 스타일 적용 
		$ 
	※ class를 지정하지 않고 CSS만으로도 깔끔하게 정리할 수 있다.
==state(상태)==, state를 다른 element와 연계해 사용할 수 있다.
	- active 클릭했을 때 
	- hover 커서를 위로 가져갔을 때
	- focus 키보드로 선택되었을 때
	- visited 링크에만 적용됨, 방문했던 곳을 색으로 구분해 줌
	- focus within 부모에 적용된 효과가 자식이 focus가 될 경우 부모의 효과가 덧씌워짐(??)
	- ==state를 다른 element와 연계해 사용할 수 있다.==
		- ex) form:hover input{} , 부모의state에 따라 자식을 바꿀 수 있다.
		- ==ex) form:hover input:focus{}, 의 형태로도 사용 가능== (사용빈도가 많다.)
Colors and ==variables(색과 변수)==
	color
		- hexadecimal color(16진수 컬러)
		- RGBA a는 투명도(opacity)
	==:root== 전체 문서(document)의 뿌리가 되는 ==변수==
		- ==변수는 dash 2개 다음에 dash1개, 그리고 변수 이름으로 지어야 함(규칙)==
		- 빈공간은 dash로 채워줘야 한다.
		- 사용시에는 var()를 통해 사용
			- style>에 :root{}를 작성,
			ex) :root{--main_color: tomato;}
			필요한 곳에서 var(--main_color);로 호출하여 사용한다.
	- custom properties 참고 [MDN](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_cascading_variables)
==Transitions== 애니메이션 효과, transition은 state에 따라 바뀌는 proprety를 가지고 있으면 사용 가능.
	- ==transition이라는 속성은 state요소가 없는 요소에 붙여야 함.==
		- ==transition:all;==은 state요소가 있는 모든 부분에 작용한다.(==가장 일반적인 방법==)
			- 특정 요소에만 효과를 주고 싶으면 해당 요소의 명을 작성
				- transison은 특정 여러 요소에 적용할 수 있고(all이 아닐때) ,(콤마)로 구분해 주어야 한다.
				- ex)transition:color==, ==border-radius;
			- ex) tansition: background-color라는 식으로..
		- ==transition에 요소가 있으면 state요소에도 반드시 해당 요소가 있어야 한다.==
		- ==transition은 state요소에 속할 수 없다.==
			- 반드시 ==root에 위치==, element에 위치해야 한다.
		- ease-in function 브라우저에 애니메이션 변화방법을 알려줌
		- cubic-bezier 자신만의 애니메이션을 만들 수 있게 해준다.
		- ==transition은 transform과 결합가능==
Transformations [transform MDN 참고](https://developer.mozilla.org/ko/docs/Web/CSS/transform) 많은 transform을 복사해서 사용 가능!
	- ==translate에서 transform:명령을 실행해도 다른 형제(sibling)는 변화 시키지 않는다.==
	- transformation은 ==box element를 변형 시키지 않는다.==
		- 다른 요소의 box를 변형시키지 않고 원하는 요소를 이동시키키 위해 사용함
		- transformation은 페이지의 픽셀의 다른 부분에 작용함(box차원에서 발생하지 않는다.)
	- trnasfrom은 여러 개의 조합이 가능하다.
	- rotate
	- skew
	- transform은 transition과 결합가능(root)
※ 이미지 삽입 시 경로 확인(깨질경우)
==Animations== 마우스 움직임 등 없이 작동하는 애니메이션
	- ==사용법==: @keyframe 애니메이션이름
		- root에 작성한다.
		- ==옵션1: from{}to{}==(2개의 단계만 있을때)
			- infinite(무한반복)사용 가능
		- ==옵션2: 0%{}50%{}100%{}== (원하는 만큼 많은 스텝을 가질 수 있다.)
		- ==적용==: 해당 element에 ==animation:== 애니메이션이름을 작성하면 적용됨
		- ex) img{
		- animation: coinflip 5s ease-in-out:
		- }
	- 애니메이션 적용시 ==transform을 권장!==
		- opacity
==Media Queries== 오직 CSS만을 이용해 스크린 사이즈를 알 수 있는 방법(반응형 웹사이트 구축 방법)[MDN 참고](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_media_queries/Using_media_queries)
	- @media query는 조건을 추가할 수 있는 방법이다.(코드의 조건이 true면 CSS실행)
	- ==사용법==: ex) ==@media screen and (){}== 더 많은 조건을 가질 수 있다.
		- screen 기기별 스크린을 위해 사용
		- print
	- @media query안에 원하는 css를 넣을 수 있다. ex) div{}, span{} 등등
		- and (max-width)
		- and (min-width)
		- and (orientation:) 휴대용 기기의 디스플레이가 가로/세로인지 확인
			- landscape 가로
			- portrait 세로
	※ and 다음 괄호()는 띄워 쓰기 해야 한다.