# Component 사용설명서

## component 사용시 주의사항

1. 이름의 앞 글자는 항상 대문자로 사용한다
(소문자로하면 랜더링이 안된다)
2. return()안에서는 태그 하나로 꼭 묶어줘야한다

## <React.Fragment>

의미없는 div로 전체를 묶기 싫을때? <></> 로 밖을 묶어서 사용할수있다

### component를 만들면 관리하기가 편해진다.

### 어떤것을 component로 만들어야할까

- 반복적으로 사용할 HTML(재사용하는 HTML)
- 자주 변경되는 HTML UI들(Ui → view)
- 다른 페이지를 만들 때도 컴포넌트로 만든다

### component의 단점

- state를 쓸때 복잡해진다(state의 생애주기 때문에 ) 
→ 상위 컴포에서 만든 스테이트를 사용하려면 props문법을 이용해 전해줄수있다

컴포넌트의 이름은 항상 대문자로 시작한다.

React는 소문자로 시작하는 컴포넌트를 DOM태그로 처리한다. 예를 들어<div/>는 HTML div 태그를 나타내지만 <Welcome/>은 컴포넌트를 나타내며 범위 안에 Welcome이 있어야한다.

[JSX 이해하기 - React](https://ko.reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized)