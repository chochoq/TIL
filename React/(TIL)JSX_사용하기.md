# JSX 사용하기

생성일: 2021년 4월 9일 오후 11:43

# JSX 문법

## 태그는 꼭 닫아준다

App.js 파일에서 실습합니다! (오류를 내면서 해보는 거예요!)

하이라이트 된 부분은 지워주세요.

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fd37cc27f-32eb-428c-811a-4e5def9852bf%2F_2020-10-04__10.49.55.png?table=block&id=1a1171a0-245a-40b3-8dcf-7194d8aa7bb1&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=1060&userId=7d16dc4d-9462-41bf-ab91-e32614e40d16&cache=v2)

```jsx
// input 태그를 닫지 않고 넣어볼거예요!
//-> input 태그는 html에서는 닫지않고도 사용이 가능하지만 jsx에서는 꼭 닫아주어야합니다
function App() {
  return (
    <div className="App">
      <input type='text'>
    </div>
  );
}
```

![](https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F74abe6a2-a720-4eb4-b8cc-4c3e4ba43ba7%2F_2020-10-04__10.52.29.png?table=block&id=f737483f-115c-4928-88d1-2ec38b358596&spaceId=83c75a39-3aba-4ba4-a792-7aefe4b07895&width=790&userId=7d16dc4d-9462-41bf-ab91-e32614e40d16&cache=v2)

JSX 문법에 맞지 않는다고 에러가 납니다! 아래처럼 /를 추가하고 브라우저를 새로고침 해봅시다.

```jsx
<input type='text'/>
```
## 태그에 className을 줘서 사용할수있다

```jsx
// app.js
import './App.css';

<div className="클래스이름">
</div>
```

```jsx
// app.css
.클래스이름{
	css주기
}
```

## 리액트에서의 데이터 바인딩(변수지정)

Binding : 받아온 데이터를 js에 저장한후 html로 넣어서 출력해주는 것 

```jsx
function App() {

  let post = "강남";

  return (
    <div className="App">
      <div className="b-nav">
        뿌에에
      </div>
      <h4> 블로그 글 </h4>
      <h4> { post }</h4>
    </div>
  );
}

export default App;
```

출력결과

![](https://media.vlpt.us/images/chocho/post/e6989538-ffd0-46e3-8742-40ed8ce352be/_2021-04-10__12.45.44.png)

중괄호를 사용해 바인딩이 가능하다.

```jsx
function App() {

  function 함수() {
    return 100;
  }

  return (
    <div className="App">
      <div className="b-nav">
        뿌에에
      </div>
      <h4> 블로그 글 </h4>
      <h4> { 함수() }</h4>
    </div>
  );
}

export default App;
```

![](https://media.vlpt.us/images/chocho/post/d1600649-f499-4a46-bfab-6916b8c2d1a2/_2021-04-10__12.47.45.png)

변수뿐아니라 함수도 바인딩이 가능하다

```jsx
import logo from './logo.svg';
import './App.css';

function App() {

  return (
    <div className="App">
      <div className="b-nav">
        뿌에에
      </div>
      <h4> 블로그 글 </h4>
      <img src = {logo} />
    </div>
  );
}

export default App;
```

![](https://media.vlpt.us/images/chocho/post/2dd7ef1b-0e53-482f-8019-bc9a9432a043/_2021-04-10__12.50.57.png)

src, id, href등의 속성에도 {변수명, 함수} 등을 넣어서 바인딩이 가능하다

## JSX에서 Style 주는 법

```jsx
function App() {
  return (
    <div className="App">
      <div style={{color: 'blue'}}> 블로그 글 </div>
    </div>
  );
}

export default App;
```

![](https://media.vlpt.us/images/chocho/post/1dfd0d6f-816f-489c-98f0-28f557b758e7/_2021-04-10__12.59.09.png)

style={object 자료형으로 만든 스타일}

```jsx
function App() {
  return (
    <div className="App">
      <div style={{color: 'blue', fontSize:'30px'}}> 블로그 글 </div>
    </div>
  );
}

export default App;
```

![](https://media.vlpt.us/images/chocho/post/d0f1e6e6-d6af-4587-947e-e158641896db/_2021-04-10__1.01.23.png)

style을 연달아 사용할 때는 ,(콤마)로 이어서 사용한다.

```jsx
function App() {

  let post = {color: 'blue', fontSize:'30px'};

  return (
    <div className="App">
      <div style={ post }> 블로그 글 </div>
    </div>
  );
}

export default App;
```

스타일 역시 변수명으로 지정해 {}에 넣어 사용할수 있다