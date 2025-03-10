[[CSS 입문]]

### 기본개념

- #HTML만이 브라우저에게 content가 어떻게 구성되어 있는지 설명할 수 있다.
- Tag를 모두 암기할 필요없다.==어떻게 작성하는지 기억해야 한다.==
- 암기보다는 검색이 시간을 절약하는 방법
- 필요 시 웹사이트를 ==검색해 tag의 이름과 attributes(속성)을 참고해라.== 
- Attribute에는 ==공백을 입력해서는 안된다==.
- Attribute의 값은 ==항상 큰따옴표("")를 사용해야= 한다.
- 모든 TAG가 ID를 갖는다.
- 모든 TAG가 src를 갖지 못한다.

### 문서기본구조

- ==<!DOCUTYP HTML>==, 모든 HTML문서는 첫 구문이 동일
- =="html(<>)로 시작, html(</>) 끝, HTML 태그로 페이지 작성
- ==head:== 해당 파트에서는 웹사이트의 환경을 설정(태그들이 브라우저에서 보이지 않음), 검색엔진이 이해 할 수있게 정리하는 것
	- head의 태그들은 보여지지 않는다.
	- title, 탭의 이름 정의
	- link
		- rel="shortcut icon"을 통해 탭의 아이콘 표시
		- href=""로 이미지 경로 호출
	- meta (부가적인 정보), self closing( />로 문장을 닫아줘야 함)
		- ==charset(중요)==, 브라우저에 표현되는 text정의
			- utf-8
		- content
		- name - description(설명)
		- "og:image" - SNS에 사이트 공유시 보여지는 이미지
- ==body:== 해당 파트에서는 웹사이트의 contens를 보여줌
	- id는 body안에 어떤 태그에든 넣을 수 있는 attribute다.
		- id는 unique identifrier, 고유식별자.
		- id는 고유해야한다.
		- ==element당 하나의 id만 가질 수 있다.(규칙)==
		- 올바른 위치에 제대로 작성해야 작동.

### 기초문법
- 주요문법
	- true와 enabled는 같은 기능이다.
		- ==기본양식을 잘 이해하자==. 암기불가
			- ==tagname attrname="attrvalue"+콘텐츠+tagname== 의 구문의 이해가 필요함.
	- h1: 헤더1 <>시작, </>끝
	- p: paragraph, 문단 text에 사용
	- span: 짧은 text에 사용
	- list
		- ol(order list): 순서가 있는 목록
		- ul(unorder list): 순서가 없는 목록
		- li(list item) 오더리스트 안에 사용
	- a(앵커): 다른 사이트로 이동을 도와준다 (==#==은 현재 페이지 머뭄)
		- target, 링크의 여는 형태 설정
			- self, 현재 페이지에서 보여줌, target ="_self"
			- blank, 새 페이지에서 보여줌
	- attributes, tag에 추가하는 부가적인 정보
	- img, img 태그는 self-closing 태그(별도로 닫아줄 필요가 없다)
		- src, img 태그의 attributes, 사진or이미지 링크 입력
		- 로컬이미지 사용시 .html파일과 함께 폴더에 두어야 한다.
		- 편집기 내 이미지 폴더 생성 시 src에 "해당폴더/파일명.확장자" 입력
	- form
			- input: (셀프클로징 태그, />으로 닫아주어야 함)
				- text
				- password text를 password형태로 박스에 표시
					- ==required== - form속성 데이터가 서버에 제출되기 전 반드시 채워져 있어야 하는 입력 필드를 명시
				- placeholder input 박스 안에 원하는 문구 표시
			- label: label for=""로 작성, for에 attribute(속성)를 작성한다.
				- label에 for를 넣었으면, **input에는 id**라는 attribute를 넣어줘야한다.
				- ==for와 id의 값은 동일해야 한다.==
				- attribute에는 공백을 넣어서는 안
- ---
