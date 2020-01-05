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
        return value;
    }

    class App extnds React.Component {
        render() {
            return value;
        }
    }

선언

react는 자동적으로 class component의 render method를 실행한다.

## state

state는 보통 동적 데이터와 함께 작업할 때 만들어진다, 변화는 데이터, 존재하지 않는 데이터 등등

    setState( { count: 1 })

state object의 count를 1로 설정한다.

setState를 사용하지 않으면 새 state와 함께 render function이 호출되지 않는다.

    this.setState(current => ({ count: current.count + 1 }));
    this.setState({ count: this.state.count + 1 });

밑의 방법보다 위의 방법을 사용해야함.

## 함수

    add = () => {
        console.log("add");
    };

    function add() {
        console.log("add");
    };

위와 밑은 같은 기능 함수

## Component Life Cycle

    componentDidMount() {}
    constructor() {}
    render() {}

실행되는 순서 constructor() -> render() -> componentDidMount()

    componentDidUpdate() {}

component가 update가 된 발생

    componentWillUnmount() {}

component가 죽을 때 발생

## ES6

    const { isLoading } = this.state;
    isLoading

    this.state.isLoading

위와 아래 모두 같은 뜻

## delay function

    setTimeout(function, time)

    componentDidMount() {
        setTimeout(() => {
            this.setState({ isLoading: false });
        }, 6000);
    }

## axios

    npm i axios

## yts api

    yts.lt/api
    https://yts-proxy.now.sh/list_movies.json

yts는 불법사이트라서 api(?)가 자주 바뀌므로 밑의 주소를 사용.

## 비동기 함수 사용

    getMovies = async () => {
        const movies = await axios.get("https://yts-proxy.now.sh/list_movies.json");
    };
    componentDidMount() {
        this.getMovies();
    }

async를 사용함으로써 await을 사용할 수 있고 await을 사용함으로써 await으로 무엇을 기다리길 원하는지(여기서는 axios) 지정.

## string.slice(start, end)

    const summary = "alskfdjlsfjdlfkdsjf fjeoifjewfoi sjldsjflk"
    summary.slice(0, 10);

0-10까지의 string 반환

## Deplying to Github Pages

    npm i gh-pages

github의 github page 도메인에 나타나게 해준다. 제일 먼저 이거 깔아야함.

1.  package.json 파일에

        "homepage": "https://hojin9622.github.io/movie_app_2019"

위 코드를 추가한다.

2.  npm run build 를 친다.

        npm run build

3.  package.json 파일의 scripts에 아래 코드를 추가한다.

        "deploy": "gh-pages -d build"

4.  package.json 파일의 scripts에 아래 코드를 추가한다.

        "predeploy": "npm run build"

deploy를 호출할때마다 predeploy를 먼저 호출한다.

5. npm run deploy를 친다.

## react-router-dom

    npm install react-router-dom

네비게이션을 만들어주는 패키지

https://www.npmjs.com/package/react-router-dom

    import { HashRouter, Route } from "react-router-dom";

react-router-dom 에는 많은 router가 있는데 여기서는 HashRouter를 사용한다.

    import About from "./routes/About";
    <Route path="/about" component={About} />

Route에는 매우 중요한 props가 한개 들어간다. 그 prop는 렌더링할 스크린 다른 prop는 뭘 할지 정해준다.

about 폴더의 About 컴포넌트

    <Route path="/" exact={true} component={Home} />

exact={true} 를 주게되면 정확한 경로에 대해서만 렌더링을 한다.

    import { BrowserRouter, Route } from "react-router-dom";

BrowserRouter는 링크에 #표시가 없다, githubpage에 정확히 설정하기 힘들다.

HashRouter는 깃허브페이지에 하기 쉬움.

## Navigation

    import { Link } from "react-router-dom";

    <Link to="/">Home</Link>

<a href>는 html 코드라서 페이지를 새로고침 한다.

react-router-dom 에서 { Link } 라는걸 사용.
