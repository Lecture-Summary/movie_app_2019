# Movie App 2019

React JS Fundementals Course(2019)

## How does React work?

React는 빈 HTML 소스에 HTML 소스를 밀어넣는다.

이러한 react만의 특징을 jsx 라고한다.

jsx = HTML + JavaScript

구글크롬 검사를하면

    <h1>Hello</h1>

body에 소스코드가 보이지만 소스보기를 클릭하면 아무 코드가 없다.

## Component

ract가 멋진 이유는 재사용 가능한 component를 만들 수 있다는 점이다.(계속 반복해서 사용가능.)

HTML을 반환하는 함수

    <App />

component를 사용하는 방법

React application은 한번에 하나의 component만 rendering 할 수 있다.

    ReactDOM.render(<App /><Potato />, document.getElementById("root"));

App component와 Potato component를 두개 사용하여 에러발생.

    <Food fav="kimchi" />

food component에 fav라는 이름의 property에 kimchi라는 value를 준다.

value에는 string뿐만아니라 boolean, array도 넣을 수 있다.
