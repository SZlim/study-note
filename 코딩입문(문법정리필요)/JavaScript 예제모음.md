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

##### 예제2(classList.contain())
```
const h1 = document.querySelector("div.hello:first-child h1");
function handleTitleClick() {
  const clickedClass = "clicked";
  if (h1.classList.contains(clickedClass)) {
    h1.classList.remove(clickedClass);
  } else {
    h1.classList.add(clickedClass);
  }
}
h1.addEventListener("click", handleTitleClick);
```

##### 예제3(classList.toggle())
```
const h1 = document.querySelector("div.hello:first-child h1");
function handleTitleClick() {
  h1.classList.toggle("clicked");
}
h1.addEventListener("click", handleTitleClick);
```

#### 예제4(search)
```
const loginForm = document.getElementById("login-form");
const loginInput = loginForm.querySelector("input");
const loginButton = loginForm.querySelector("button");
```

#### 예제4(getting username)
```
const loginForm = document.querySelector("#login-form");
const loginInput = document.querySelector("#login-form input");
const greeting = document.querySelector("#greeting");
const HIDDEN_CLASSNAME = "hidden";

function onLoginSubmit(event) {
  event.preventDefault(); //submit 방지
  const username = loginInput.value;
  loginForm.classList.add(HIDDEN_CLASSNAME);
  greeting.innerText = `hello ${username}`;
  greeting.classList.remove(HIDDEN_CLASSNAME);
}

loginForm.addEventListener("submit", onLoginSubmit);
```

#### 예제5(object array) - string object
```
let myArray = [
  { name: "John", age: 30 },
  { name: "Jane", age: 25 },
  { name: "Peter", age: 35 }
];

console.log(myArray[1].name); // "Jane"
```
