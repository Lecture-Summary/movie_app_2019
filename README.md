# Movie App 2019

React JS Fundementals Course(2019)

## How does React work?

React는 빈 HTML 소스에 HTML 소스를 밀어넣는다.

구글크롬 검사를하면

    <h1>Hello</h1>

body에 소스코드가 보이지만 소스보기를 클릭하면 아무 코드가 없다.

## Component

HTML을 반환하는 함수

    <App />

component를 사용하는 방법

React application은 한번에 하나의 component만 rendering 할 수 있다.

    ReactDOM.render(<App /><Potato />, document.getElementById("root"));

<App /> component와 <Potato /> component를 두개 사용하여 에러발생.
