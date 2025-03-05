
###### 순서
- HTML작성한 다음 HTML의 element를 가져와 javaScript로 작업한다.
#### input Values
- tip: input과 button을 많이 사용할 경우, HTML에서 div안에 넣어, class로 만들자.
- HTML에서 element에 id를 부여한 경우, ==document.queryselector()에서 반드시"# + id명"을 입력해야, 해당 id를 javascript가 찾을 수 있다.==
	- 단, .getElementById()는 id를 추적하기때문에 id명만 정확히 넣어주면 됨.
- const로 선언된 HTML element(.document)를 통해 좀 더 정밀한 조사가 가능하다. ==해당 선언된 const안에서 queryselector()를 통해 범위를 좁혀 원하는 목표를 찾을 수 있다.==