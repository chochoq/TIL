# (TIL) props, state

# React Props

props는 변하지 않는(Immutable Data) 데이터이다. 

상위(부모) 컴포넌트에서 하위(자식) 컴포넌트로 데이터를 전할 때, props가 사용된다.

## React Props

```jsx
// Car 요소에 "brand"속성을 추가한다.

const myelement = <Car brand="Ford" />;
```

구성 요소는 인수를 props객체로 받는다

```jsx
// 구성 요소에서 "brand" 속성을 사용한다.

class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand}!</h2>;
  }
}
```

## Pass Date

prop은 데이터를 매개변수로 전달할 수 있다.

```jsx
//Garage컴포넌트의 "brand"속성을 Car컴포넌트로 보낸다.

class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand}!</h2>;
  }
}
```

```jsx
class Garage extends React.Component {
  render() {
    return (
      <div>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" />
      </div>
    );
  }
}

ReactDOM.render(<Garage />, document.getElementById('root'));
```

전송할 변수가 있고 위의 예에서와 같이 문자열이 아니라면 변수 이름을 중괄호 안에 넣는다

```jsx
class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand}!</h2>;
  }
}
```

```jsx
//"carname"이라는 변수를 만들고 Car 구성 요소로 보낸다.

class Garage extends React.Component {
  render() {
    const carname = "Ford";
    return (
      <div>
      <h1>Who lives in my garage?</h1>
      <Car brand={carname} />
      </div>
    );
  }
}

ReactDOM.render(<Garage />, document.getElementById('root'));
```

객체 일 때,

```jsx
class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand.model}!</h2>;
  }
}
```

```jsx
class Garage extends React.Component {
  render() {
    const carinfo = {name: "Ford", model: "Mustang"};
    return (
      <div>
      <h1>Who lives in my garage?</h1>
      <Car brand={carinfo} />
      </div>
    );
  }
}

ReactDOM.render(<Garage />, document.getElementById('root'));
```

## Props in the Constructor

컴포넌트에 생성자 함수가있는 경우 props는 항상 생성자 및 super()메서드 를 통해 React.Component에 전달되어야한다.

```jsx
class Car extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <h2>I am a {this.props.model}!</h2>;
  }
}

ReactDOM.render(<Car model="Mustang"/>, document.getElementById('root'));
```

props는 읽기전용이라, 값을 변경하려고 하면 오류가 발생한다.

# React State

컴포넌트에서 유동적인 데이터를 다룰 때, state를 사용한다. React.js 어플리케이션을 만들 땐, state를 사용하는 컴포넌트의 갯수를 최소화하는 것을 노력해야한다.

---

props와 state는 생긴 건 비슷하지만 용도는 다르다. 헷갈리지 않게 다음 특성을 기억하자.

<img width="100%" src="https://images.velog.io/images/chocho/post/ea06e965-99ed-4406-af79-cac3feeff6db/_2021-03-30__8.34.58.png">
---

출처

[React State](https://www.w3schools.com/react/react_state.asp)

---

[4.4 노드의 속성/Props 정의하기](https://hayanmind.gitbooks.io/react-enlightenment-in-korean/content/react-nodes/4.4.html)

[React 3 | Props 와 State](https://medium.com/@yms0214/react-3-props-%EC%99%80-state-cf8cbf37d0e7)

[(React.js) React.js의 props 사용방법](https://medium.com/@yeon22/react-js-react-js%EC%9D%98-props-%EC%82%AC%EC%9A%A9%EB%B0%A9%EB%B2%95-bc59a5c257a)