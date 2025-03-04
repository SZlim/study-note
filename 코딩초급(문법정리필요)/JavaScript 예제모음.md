##### 예제1 (CSS in javascript)
```
const h1 = document.querySelector("div.hello:first-child h1");
function handleTitleClick() {
  const currentColor = h1.style.color; // getter로 const로 변수 선언
  let newColor; // setter로 사용하기 위해 let으로 변수 선언(변수값 변경가능)
  if (currentColor === "blue") {
    newColor = "tomato";
  } else {
    newColor = "blue";
  }
  h1.style.color = newColor; //setter
}

h1.addEventListener("click", handleTitleClick);
```