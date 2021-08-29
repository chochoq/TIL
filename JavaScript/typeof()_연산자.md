# typeof() 연산자


사용하는 값이 어떤 자료형인지 알 수 있다.

```jsx
console.log(typeof 101);    //number
console.log(typeof 'hi');   //string
console.log(typeof true);   //boolean

console.log(typeof 10.1);   //number
```

변수뿐아니라 함수에서도 사용이 가능하다.

```jsx
let name = 'chocho';
function sayHello(){
	console.log('Hello');
};
```

```jsx
console.log(typeof name);      //string
console.log(typeof sayHello);  //function
```

연산식을 넣어서 typeof사용하기

```jsx
console.log(typeof 'Hello' + 'chocho');  //stringchocho
console.log(typeof 8 - 3);                 //NaN(not a number)
```

**`typeof 8 - 3`**는 연산 우선순위에 따라, **`typeof 8`**의 결과인 문자열 'number' 와 숫자 3의 뺄셈이 됩니다.
선택지 2를 다시 정리하면 **`'number' - 3`** 가 되는데요, 문자열과 숫자는 뺄셈을 할 수 없기 때문에, 결과는 **`NaN`**이 됩니다.

연산자의 우선순위를 높여주면 제대로된 값이 나온다.

```jsx
console.log(typeof ('Hello' + 'chocho'));  //string
console.log(typeof (8 - 3));                 //number

```

---

[연산자 우선순위 - JavaScript | MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)