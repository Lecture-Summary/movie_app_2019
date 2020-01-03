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

## map

map은 array의 각 item에서 function을 실행하는 array를 가지는 javascript function이며 그 function의 result를 갖는 array를 출력한다.

    const friends = ["dal", "mark", "lynn", "japan guy"];
    friends.map(current => {
        console.log(current);
        return 0;
    })
    friends.map(function(current) {
        console.log(current);
        return 0;
    })
    friends.map(current=>{
        return current+1;
    });

사용법

    [2, 3, 4, 5]

결과

## react key

react는 똑똑하지 않기 때문에 component마다 key property를 부여해야한다.

## npm i prop-types

prop-types는 전달반은 property가 내가 원하는 property인지 확인해준다.

    npm i prop-types

    "dependencies": {
        "prop-types": "^15.7.2"
    }

install 후 package.json 파일에서 dependencies를 보면 정상적으로 설치되었는지 확인 가능.

    Food.propTypes = {
        name: PropTypes.string.isRequired,
        picture: PropTypes.string.isRequired,
        rating: PropTypes.number.isRequired
    };

        rating: PropTypes.number

사용법, property에 string이 필요하면 string.isRequired, number가 필요하면 number.isRequired

array인지 boolean인지 object 인지도 체크가능하다.

isRequired를 생략하면 type만 체크한다.

## function, class Component

    function App() {

    }

    class App extnds React.Component {

    }

선언

## state

state는 보통 동적 데이터와 함께 작업할 때 만들어진다, 변화는 데이터, 존재하지 않는 데이터 등등
