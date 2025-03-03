
==**index.html(첫번째라는 의미) part.1**==
	-대부분의 웹 서버가 디폴트로 index.html을 검색하도록 설정이 됨
==class==
	하나의 텍스트가 아닐 경우, 각각의 class로 CSS가 인식함.
	ex) class=btn btn-big btn__price (3개의 class)
==BEM(block, element, modifier)==
	-CSS작성시 편의를 위해 모든걸 class로 사용(대부분의 프로그래머가 동의)..(id무시)
	-코드를 읽기가 편해짐
	-단점: class가 엄청 커짐
	- 규칙
		- .btn{} 블럭
		- .btn__price{} 엘레먼트
		- .btn--orange{} 모디파이어
	-column, box, line 등 흔한 이름(class)은 ==구분이 가능한 이름(class name)으로 만들어야 함==
		반드시 class 이름을 작성할 경우 하나의 텍스트가 되도록해야함.
		ex)stausbar__column(띄워쓰면 2개의 class가 됨.)
		부모/자식이 무엇인지 같이 적어주는 것이 포인트.
==HTML주석 처리 방법:== <!-- --> ,프로그래머만 볼 수 있는 코드
==CSS 주석 처리 방법:== /* 시작, 끝(반대)
==icon 생성 관련..==
	직접구하기 
		heroicons.dev - 필요 아이콘의 svg를 복사, 사용
		==fontawesome== - 코드킷을 script로 ==html의 body에 첨부==해서 사용(추천, 무료라 제한적)
			스크립트 삭제 시 해당 코드킷은 작동하지 않음
			==스크립트==: ==항상 마지막에 위치해야 함 body 태그가 닫히기 직전에 위치!==
		fontawesome 아이콘 크기 설정방법
			해당 아이콘의 사이즈 별 HTML코드를 복사/사용
		==SVG==: fixel이 아닌 path로 되어 있는 이미지.(수학과 좌표) [SVG MDN참고](https://developer.mozilla.org/ko/docs/Web/SVG)
	==icon은 text/font와 같다고 생각하면됨.==
		rgba로 컬러 변경 가능 R
==header==
	header마다 class를 생성해 헷갈리지 않도록 한다.
==form==(form의 갯수가 많아 지면 class로 각각 구분해 줘야 한다.)
	- ==form의 중요 attribute(속성)== (추후, 유튜브 클론코딩을 참고)
		- action 어떤 페이지로 data를 보낼지 지정, 해당 페이지의 html이 있어야 작동. 
		- method
			- post 백엔드 서버에 정보를 전송하는 방식(서버필요)
			- ==get 보안에 취약함.==(url에 해당 정보가 노출됨) ==절대, username/password는 get방식으로 보내면 안됨.== URL에 포함되어도 상관없는 정보들을 get방식으로 전송.
				- get
		- require ??? 검색필요...
	- input: type은 text와 password, 각각 name 지정필요
		type
			text
			password
		placeholder
	- ==btn(버튼):== form에서 btn은 input type=submit
		submit의 value는 필요한 이름 기입
			button테그로도 작성가능
	- 
button
==a(링크)==
	#, 현재페이지에 머뭄을 의미
==CSS(html의 head에 작성)==
	- 숏컷: link:css, css파일을 import하기 위해 반드시 폴더의 경로와 일치시켜야 한다.
	- ==.클래스명{} : 클래스 호출시 . 으로 호출==
		아이디는 #아이디명{}으로 호출
		테그는 테그명{}으로 호출
	- ==display:flex== 같은 열에 element배치
	- ==flex-direction:== flex로 배치한 element을 배치할 축 결정. 
		- ex)column or row
	- ==aline-item==: 요소를 한 줄(같은 축)에 일렬로 배치 (중심/좌/우 등등)
	- ==:first-child & nth-child(숫자)&last-child==로 class 내 개별 속성을 적용할 element를 호출
	- ==justify-contents==: 객체 간 간격 설정,main axis(주축)을 따라 움직임(옵션 다양함.)
		- 같은 간격으로 유지 옵션, space-between
	- margjin/padding간격
		- ex) mrgin: 0px 3px;(위아래 간격0, 좌우3px 의미)
	- font-family: css를 통해 body전체에 적용(옵션 다양함)
		- 구글폰트를 통해 다양한 폰트를 검색/적용가능
			- 원하는 글꼴을 CSS에 import하는 방식으로 추가하는 것을 추천함.
			- import style부분 복사
			- 적용: css내용의 fontfamily부분 복사
		- 필요한 font만 추가!!모든 font를 추가하면 웹사이트가 무거워진다.
==import==
	필요한 파일/경로를 메인css파일에 import해 사용
	==방법:@import "경로/url";==
==margin killing== 기본 브라우저의 스타일을 없애고 직접 디자인하는 것이 더 나은 방법이다.
	- ==reset.CSS==: 대부분의 tag에 margin 0px, padding 0px, border 0px을 적용함
		- ==reset.CSS를 만들어 문서 전체에 적용.
			코드는 인터넷복사.
		- 메인CSS(style.css)문서에 import해서 사용
		- CSS파일에 추가해 사용하는 것을 추천.(html에 link가 많이 생성되면 헷갈림)==
input border killing
	==border:none==
	border line color: rgba(0,0,0,0)
		rgba의 마지막 a는 opacity 소수점값으로 조절(1은 불투명), rgb(0.0.0)은 black이다.
	==id element::att== >> ==peseudo selector== 세부적으로 엘레먼트를 선택하게 해준다.	
input border killing 2
	input선택 시 outline을 삭제할 수 있다.
		==방법: input:foucus{ outline: none;}== ,input요소에 att적용을 위해서는 :로 추가한다. ex)input:focus{}
			1. style.css에 작성
			==2. reset.css에 작성, 전체 웹페이지에 focus lined을 삭제 원할 경우 reset.css에 작성하면 된다.==
글자색 변경
	opacity:  투명도 조절로 검~회색 조절 가능
	기타: color 값으로 변경
함수, 반드시 해당 css파일은 메인 css에 import해야한다.
	:+함수명, ex):root{},root에서 작동하는 함수
	css로 저장하고 적용을 위해서는 ==메인css에 @import한다.==
	함수호출은 ==var(함수명)==으로 실행
==CSS:not()== [:not() MDN참고](https://developer.mozilla.org/ko/docs/Web/CSS/:not)
	==:not([att]), not안의 att가 **아닐 때**, 지정 효과를 적용함.==
		[]의 역할, attribute selector
	적용: id or class element:not([att]){}
		ex) #login input:not([type="text"]){}
cursor:pointer; 커서포인터를 변경할 수 있다.
	옵션이 다양하다. not aollowed, progress 등
==text==
	align 정렬
	decoration 밑줄(장식), 제거 none
==color:inherit;== 텍스트 색을 부모로부터 받는 것
	*a 앵커의 기본 색은 ==blue*==, 기본 색상 제거방법,
		ex).nav__ling{color:inherit;} , 부모에게 색을 상속받으면 기본 컬러는 제거된다.
	- reset.css에 color:inherit 이후, 원하는 클라스에 원하는 색상을 사용해도 무방하다.
	- 특정색을 지정할 경우가 아니라면, ==reset.css에 해당 색의 속성을 부여==한다.(전체문서에 적용됨.)
**==friends HTML part.2==
		==tip== 다음 페이지 작성을 위해 제일 처음 만들 페이지 복사 후, 필요한 것만 사용.
navigation bar
	==nav vscode shortcut==
		==숏컷:== ==nav>ul>li X 원하는 갯수==> a, 원하는 갯수 만큼의 li에 a(앵커)가 자동 생성됨.
			※생성된 상태에서 필요한 곳에 입력 후, tap만으로 이동 가능
			==a(앵커) 네임에 아이콘 삽입 시, fontawesome에서 본인의 버전 확인,, fa-lg 아이콘 크게..==
	nav안에서 작업
		ul: 대부분의 nav는 ul로 나뉨
			li: ul안에 많은 li를 가짐
		구글도 nav를 찾아 ul의 li안에 있는 link를 가져오게끔 설정이 되어 있음.
	많은 요소를 다룰 때 class가 유리함.BEM규칙을 준수!
		ex) nav, nav__list, nav__btn, nav__a
	==※새롭게 CSS 파일을 생성시, 반드시 메인CSS파일에 import해야한다.== ex)@import "components/abc.css" ;(경로도 같이 입력)
**position:fiexd**
	객체의 위치를 고정할 때 사용함. 
	객체 고정 후, top, bottom 등으로 위치 조정(경우에 따라 width값이 필요할 수도 있음.)
==box-sizing: border-box== Border-box, 사용: 
	CSS에 해당box의 사이즈를 변경하지 않게 끔 알려주는 명령
		paddig(좌우)과 width100% 가 동시에 적용될 경우 CSS는 box를 padding만큰 더 늘려서 원하는 내용이 보이지 않을 수 있기에 box-sizing:border-box를 사용해, 임의로 제한
==position:absolute;==
	가장 가까운 relative 부모를 기준으로 이동
		ex) ==div가 relative가 아닌 경우 body를 기준으로 이동==. 이때 div를 relative로 할 경우, div를 기준으로 이동함.
		- top/right/bottom/left의 속성을 사용가능
Screen Header
	자주 사용하게 될 요소들은 componets로 만들어 두자
user-component(현 프로젝트 외에도 자주 사용될 요소는..)
	class로 만들어 두자. 자주 사용할 예정
	==숏컷: .class이름__요소이름X숫자(갯수)==
		원하는 만큼 동일한 class를 만들 수 있다.
	==tip: ==반복되는 것들은 component로 만들면 작업이 수월해 진다.==
이미지 수정
	==사용이 많은 양식의 img는 modifier를 만들어 사용하면 편리하다.==
	ex) img class="user user-avatar" 두개의 class명을 만들어(띄어쓰기 필수), 각각 css 파일에 효과를 작성 사용.
		소스는 동일하고 적용되는 효과만 달라진다.
간격
	페이지 마다 동일한 간격(margin)이 사용될 경우, 함수로 만들어(:root{}경로 아래)사용하면 편리하다.
main
	필요한 요소를 하나의 box에 담을 때 main을 사용.
==class 추가 적용,== 
	하나의 class 효과를 유지하면서 다른 class를 만들어 효과를 적용하고 싶을때, ==새로운 class를 기존 class 뒤에 생성==(같은 문장을 2번 적지 않아도 된다.)
	ex) div class="text-size__normal text-size__normal-not bold"
==CSS class separate(분리)==
	동일한 속성이 부여된 class를 다른 속성을 부여하기 위해 분리.(기존 유지, 특정 속성만 분리/부여)
		윗 줄에 작성해 적용 속성 분리
==father/child 분리
	father에 영향을 받는 child는 div로 분리해 영향을 받지 않게 할 수 있다.==
nav bar 수정(다른페이지 작성 및 경로 추가)시, 최초 페이지에서 링크 경로를 수정해야 
	ex)friends.html 완성, chat.html 작성 중
	nav-bar에 chat.html으로 이동 경로는 fiends.html에 우선 작성해 줘야한다. 
main-screen 
	각 페이지마다 패딩 적용 달라지거나 혼란해 질 수있으므로, class로 만들어 전체에 적용되는 변수를 적용, 통일감 유지.
	ex).main-screen{ padding: var(abc);}
negative margin
	-(마이너스)로 px 등을 적용하면 됨.
==Find information==
	==숏컷==: 같은 class명의 div를 여러개 생산시 
	 ==.클라스명 X 숫자(원하는 만큼)==
	 추가로 div 내 span을 생성을 원할 경우 ==+ > + span==
	  ex).open-chatx2
flex-direction
		display:flex 된 요소들의 축 결정
		==flex-direction 이후,== main 축은 옵션값이 메인
		ex)flex-direction:colum; 메인축은 세로축이된다. cross axis는 가로축이 된다.
	row: 객체가 가로 정렬
	column: 객체가 세로 정렬(다음 줄에 정렬?)
		축이 바뀐 상황에서 cross axis에 정렬을 하기 위해서는 align item 사용.
border line 
	자주 사용되어 지는 border line은 함수로 만들어 사용하면 편리함.
title and span
	타이틀 h1 등등 다음은 span으로 작성하는 것
	==span은 inline요소 이므로, block으로 변경해 원하는 효과를 적용한다.==
대문자/소문자
	대문자는 디자인요소, HTML 내에서는 소문자로 작성하고 ==CSS에서 대문자로 변경==한다.
	css, ==text-transform:==
		옵션: none, ==uppercase:대문자변경==
		lowercase:소문자 변경,capitalize: 각 단어의 첫글자 대문자 변경
divider(분리)
	divider효과(다른 요소도 가능할 듯..)를 사용할 경우 ==CSS에 부모 class명 뒤에 붙여서 사용하는 것을== 권장. 문장이 길어지면 다른 divder가 존재 할 수 있으므로,,,(해당 부모안의 divider만 속성 적용됨.)
	==방법:== width:1px;, height:10px, _background-color:rgba_ 로 세로 divider를 만든다.
==flex
	이미 flex상태인 column(div는)은 최상위의 부모를 찾아 정렬상태를 수정해야 한다.==
==position:absolute;==
	abasolute 포지션의 객체는 relative 포지션의 부모를 찾아서 최상위에 정렬한다.
	==단, relative 부모가 없을 경우 최 상위 body에 정렬됨==
	위치 조정은 relative 포지션의 부모의 위치에서 조정.
		absolute children need realtive father!!
screens
	동일한 components에 사소한 변경을 주기위해서는 screen을 생성해 조정한다.
		반드시 생성 후 style.css에 import
	==메인 class에 덧붙여 screen에서 생성한 class를 사용한다.==
flex container(정렬) 이해필요.6.26강의 재수강
	아이콘과 text 들을 정렬할때는 flex container가 필요하다. 상위 div
		정렬은 container내에서 1차 설정.
		정렬할때 가장 유용한 것은 flexbox이다.
a(앵커)
	아이콘을 통해 링크를 이동해야 할 경우,
	아이콘은 a(앵커)안에 존재 해야한다.
	ex) <앵커+경로><아이콘></앵커>
	아이콘 뿐만 아니라. div 전체를 경로로도 만들 수 있다.
아이콘과 span
	아이콘을 span에 넣어 사용하는 이유는 css를 사용하기 위함이다.
==kokoa Setting part==
==숏컷==header내 class명을 가진 div를 만드는 방법
	==header.class명>div.class명X숫자(원하는 만큼)==
margin 0 auto
	사용예 3개의 column에 각 right/left에 auto적용, 가운데 column이 정중아에 위치하도록 만듬(setting html/alt-screen css참고)
==Chat screen part==
헤더아이콘 간격
	.alt-header__column:last-child span:not(:first-child) {margin-left: 20px;}
	이나, 아니면
	.alt-header__column span:last child{margin-left: 20px;} 로 적용가능, 둘다 동일.
==객체고정(fixed하게 되면 이전 box들과 레이어가 분리되어 별도의 레이어를 가진다.)==
	Css에 작성해서 객체를 고정할 수 있다.(부모)
	position:fixed로 고정,(부모에 적용)
	width가 필요 = 100%, 그리고 일부 객체가 보이지 않을경우 box-sizing을 통해 border-box적용.
		fixed뒤의 객체들은 margin-top을 적용해 화면에 표시
==z-index==(레이어 개념)
	div가 있는 위치가 맨앞에서 부터 몇번째인지 나타냄,즉, layer의 순서가 몇번째인지를 나타냄.
	z-index는 절대적위치(absolute position)이나 고정된 위치(fixed position)에 대해 설정할 수 있음.
==flex direction이 column이면 cross axis는 수평이된다.==
==span block==
	span은 block이 되어야 마진을 넣을 수 있다.
border radius
	각 모서리 마다 radius값을 줄 수 있다.
	ex) border-top-left-radius
==modifier==
	하나의 class를 가진 객체에 다른 class를 추가 작성해 modifier로 사용한다.
	ex)class="message-row ==message-row--own==(모디파이어 부분)
==order==
	==flex의 children에만 적용,==
	order: 0,1등의 숫자로 flex children의 순서를 변경
	단점, 코드가 길어진다.
	==대안== ==flex-direction:row-reverse;== _html을 수정하지 않고 순서를 변경할 수 있다.
		
input width
	input width(100%)는 상위 container가 width를 가지지 않으면 적용이 되지 않는다.
	==해결== css에서 해당 container에 child순서를 지정해 직접 적용.
	ex)first child 10%
	last child 90%
	적용객체 width 100%
Direct children
	first/last child 선택 시 부모 바로 아래의 direct children선택은 '>'를 입력해 선택할 수 있다.
	ex)reply:lastchild > i
==absolute포지션일 경우== 위치는 객체의 위치는 일일이 top/right/left/bottom등으로 일일 조정해야 한다.(귀찮음)
==Splash screen part==
	position:==absolute인 객체==는 ==relative인 부모가 없을 경우 body를 기준으로 정렬==(모든 객체의 위에 정렬한다.)
	화면크기
		100vh screen height
		100vw screen width
		100% 100% of the parent(부모)
	==애니메이션==
		==css로는 한계가 있음, ==작동 후 element들이 이전상태로 되돌아감.
			문법- ==@keyframe{from{}to{}}==
			이후, 해당id/class에 animation: 이름 1s(시간) ease-in-out;(옵션)
		==해결방법:== ==forward옵션,== 애니메이션이 끝난 상태를 유지해줌.(마지막 keyframe을 기억함. )
			==문제점== 애니메이션이 결과대로 끝이 나도 그 element가 존재해 다른 element에 영향을 끼친다.
			==대안== - ==visbility:hidden;== 해당 애니메이션 element를 html상 존재하나 마우스에 적용되지 않게 빠져버리게 만드는 것
				==문제점==
				중요한 정보 등을 숨길때는 해당 테크닉을 사용하면 안된다.(정보가 HTML상에 그대로 존재하기때문에.)
		animation-delay
			애니메이션을 원하는 시간만큼 지연 시킬 수 있다.
	애니메이션 2
		0%{},50%{},100%{} 각 구간별 에니메이션을 별도로 지정할 수 있다.
		infinite옵션 - 해당 에니메이션을 지속해서 작동
	애니메이션 3
		특정 애니메이션이 마우스가 올려지면 작동하게 하기위해서는 ==:hover옵션==이 필요함(css에 작성)
	==will-chagne==(브라우저에게 무언가 바뀔거라고 알려주는 명령어)
		애니메이션 렌더링을 돕는 것(==애니메이션 GPU가속화==)
		ex)will-change:transform;(변화할 속성에 적용 예시는 transform)
	==animating chats screen==
	==Fade in 애니메이션==
		from과 to를 사용해 opacity를 조정,(0 -> 1) 
		디테일- from: transform:translateY()을 입력, to: transform: none을 적용
	==focus within==
		의미: form내부의 element가 focus가 되어 있다면..다음을 실행해라.(focus element를 찾는다.)
	==transform==을 통한 상태변화를 적용하기 위해서는 반드시 해당 객체 상위 부모에게도 transition을 입력해 주어야 한다.
==No mobile Media query== part
오직, 휴대폰 화면으로만 화면이 보이게 하는 방법
	@media screen and (max-width: px)는 해당 화면의 width가 특정(지정)사이즈 보다 크면 특정 CSS를 작동시키는 방법
		@media screen이 작동될려면 작동 조건 CSS코드가 필요하다.
==git== 마스터와 브랜치의 기능으로 1개의 파일로 서로 다른 버전의 파일을 가질 수 있다.
	master 
	branch - branch는 master로 merge가 가능하다.
		branch에서 업데이트된 최종본은 master상태에서 branch - merge into current branch로 병합이 가능하다.
	branch가 있을 경우(특별한 이름의 특별한 branch),git hub에서 공짜url을 제공(==static website== - HTML,CSS,JavaScript로만 이루어진 사이트)
		룰 1. make a branch
		룰 2. branch name '==gh-pages==' gh-pages를 생략 할 경우 publish를 할 수 없다.
		룰 3. repository is shuld be a public.
			저장소가 private일 경우 public 웹사이트로 만들 수 없다.
				tip: 대문자로 웹사이트의 css가 작동 안할 경우 터미널에서 해당 폴더 터미널로 이동, git mv 폴더이름 temp 
				이후, git mv temp 폴더이름
---
	
- CSS HACK(따로 파일로 만들어 놓은 것을 추천)
	- space-between으로 해결하기 어려운 정중앙배치를 가능하게 해줌.
	- 적합한 파일명.css를 생성 후 메인css파일(style.css)에 @import해서 사용.
tip
	- 메인css(style.css)는 다른 css를 @import하는 용도로 사용하는 것을 추천함.(가독성up,깔끔)
	- style.css(메인)에는 font-family와 같이 모든 스크린에 적용될 수 있는 스타일을 작성
		- 문서 전체의 색상도 지정 가능
	- CSS파일 내에서 파일의 순서를 지키는 것은 중요.(cascading)
		- ex)메인 font를 특정css파일 아래에 배치할 경우 font family가 적용이 안된다.
	- ==span은 width와 height를 가지지 못한다. ==
		- 필요시 display: block; 블럭으로 변경해 사용한다.
	- CSS작성 시==class는 class끼리 추가가 가능. ,(세미콜론)으로 구분 ex) .user, .user-name{}
		- class내 modifer(class)를 적용할 때는
		- ex)Class="message-row ==message-row--own==(모디파이어 부분)
	- 파일 작성 후 에러/페이지에 적용이 안될 경우 우선, @import를 했는지 체크해야 한다.
	==- border 안쪽에 간격을 주는 방법
		 padding
	- icon도 font-size로 조절가능.
	-==CSS에서 `display: flex;`의 의미와 사용법==
==`display: flex;`==는 CSS 속성 중 하나로, 웹 페이지의 레이아웃을 구성하는 데 사용되는 매우 강력하고 유연한 방법인 **Flexbox**를 활성화하는 역할을 합니다. Flexbox는 요소들을 원하는 방향으로 정렬하고, 공간을 효율적으로 배분하며, 다양한 화면 크기에 대응하는 반응형 디자인을 쉽게 구현할 수 있도록 도와줍니다.[flex 참고](https://docs.google.com/document/d/13YuzmQyFjr6sx4mYNxKKRXSUJ90PBHkt0FT700OrMHw/edit?pli=1&tab=t.0))
==화면크기==
	100vh screen height
	100vw screen width
	100% 100% of the parent(부모)



보충학습필요
	==정렬방법==
	- ==justify-contents==: main axis(주축)을 따라 움직임
	- ==align-items==: cross axis(교차축)을 따라 움직임 
	- status-bar 고정하는 방법 공부
	- badge작성 및 위치 적용법.
	- 화면에 크기가 변해도 행 간격이 일정하게 보이는 방법.
	- margin auto