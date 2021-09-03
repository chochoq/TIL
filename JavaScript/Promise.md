# Promise


JS는 싱글쓰레드로 동작을 하는 언어

대표적인 비동기작업 WebAPI(ajax, setTimeOut, dom), Firebas

[자바스크립트 11. 비동기 처리의 시작 콜백 이해하기, 콜백 지옥 체험 😱 JavaScript Callback | 프론트엔드 개발자 입문편 (JavaScript ES6)](https://www.youtube.com/watch?v=s1vpVCrT8f4)

# hoisting

콜스택, 콜백큐, 이벤트루프,

> **콜백함수**
어떤 함수에 인수를 넘겨주는 함수

비동기에서 말하는 콜백함수(JS에서의 콜백함수)→ JS가 비동기 처리를 하기위한 패턴 중 하나(콜백패턴)

![Promise%20b1db7555fb194255b45941fa5aaea0c6/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-05_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.23.23.png](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F883b0240-406e-4fb9-a4ca-b6784a55ebe4%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-05_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.23.23.png?table=block&id=b1db7555-fb19-4255-b459-41fa5aaea0c6&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=770&userId=&cache=v2)

Hoisting은 변수 및 함수 선언이 작성한 코드의 상단으로 옮겨지는 것으로 알려져있지만, 실제로는 변수 및 함수 선언은 컴파일 단계에서 메모리에 저장되지만, 코드에서 입력한 위치에

호이스팅(hoisting)은 [ECMAScript® 2015 언어 명세](https://www.ecma-international.org/ecma-262/6.0/index.html) 및 그 이전 표준 명세에서 사용된 적이 없는 용어입니다. 호이스팅은 JavaScript에서 실행 콘텍스트(특히 생성 및 실행 단계)가 어떻게 동작하는가에 대한 일반적인 생각으로 여겨집니다. 하지만 호이스팅은 오해로 이어질 수 있습니다.

예를 들어, 호이스팅을 변수 및 함수 선언이 물리적으로 작성한 코드의 상단으로 옮겨지는 것으로 가르치지만, 실제로는 그렇지 않습니다. 변수 및 함수 선언은 컴파일 단계에서 메모리에 저장되지만, 코드에서 입력한 위치와 정확히 일치한 곳에 있습니다.

**var**

함수의 최상위로 호이스팅이된다.
선언은 호이스팅이 되고 할당은 호이스티잉 되지않는다.

**const, let** 

호이스팅이 불가하다.

JavaScript에서의 비동기작업

WebAPI(setTimeout, Ajax, Dom ), firebase

## Promise

자바스크립트는 싱글 쓰레드로 동작하는 언어입니다. (메인 쓰레드 하나와 콜스택 하나로 구성되어 있어요!)
그리고 비동기 작업을 동시에 할 수 있어요.
오잉?🤢  1번에 1개의 작업만 할 수 있는데, 어떻게 동시 실행을 할까요?
→ 자바스크립트는 코어 엔진만 가지고 돌아가지 않아요! 
실행환경(런타임)의 도움을 받아 동시 실행을 합니다.
(**WebAPI(dom, ajax, setTimeout...)**, Task Queue, Event Loop 등과 함께 동작합니다.)

- 3) 콜백이란?

    어떤 함수에 인수로 넘겨주는 함수를 콜백함수라고 부른다

    JS에서의 콜백은 자바스크립트가 비동기처리를 하기위한 패턴 중 하나이다.
     전통적인 콜백 패턴은 일명 콜백 헬로 불리는 엄청난 중첩 문제가 생기기 쉽습니다.

    1. 콜백 헬

        꼬리에 꼬리를 무는 비동기 처리가 늘어나면 호출이 계속 중첩되고, 코드가 깊어지고, 관리는 어려워집니다. 이런 깊은 중첩을 **콜백 헬**이나 **멸망의 피라미드**라고 부릅니다.

        ```jsx
        function async1('a', function (err, async2){
        	if(err){
        		errHandler(err);
        	}else{
        		...
        		async2('b', function (err, async3){
        			...
        		}){
        			...
        		}
        	}
        });
        ```

        - 이런 콜백 헬이 발생하는 이유?
            - 비동기 처리 시에는 실행 완료를 기다리지 않고 바로 다음 작업을 실행해요.
            - 즉, 순서대로 코드를 쭉 적는다고 우리가 원하는 순서로 작업이 이뤄지지 않습니다.
            - 비동기 처리 함수 내에서 처리 결과를 반환하는 걸로는 원하는 동작을 하지 않으니, 콜백 함수를 사용해 원하는 동작을 하게 하려고 콜백 함수를 씁니다.
            - 이 콜백 함수 내에서 또 다른 비동기 작업이 필요할 경우 위와 같은 중첩이 생기면서 콜백 헬이 탄생하죠. 😢
- 4) 프라미스란?

    비동기 연산이 종료된 이후 결과를 알기 위해 사용하는 객체입니다!
    프라미스를 쓰면 비동기 메서드를 마치 동기 메서드처럼 값을 반환할 수 있어요.
    전통적인 콜백 패턴으로 인한 콜백 헬 때문에 ES6에서 도입한 또다른 비동기 처리 패턴입니다.
    **비동기 처리 시점을 좀 더 명확하게 표현할 수 있어요!**

    1. 프라미스 생성
        - 프라미스는 Promise 생성자 함수(new 키워드 기억하시죠!)를 통해 생성합니다.
        - 비동기 작업을 수행할 콜백 함수를 인자로 전달받아서 사용합니다.

        ```jsx
        // 프라미스 객체를 만듭니다. 
        // 인자로는 (resolve, reject) => {} 이런 excutor 실행자(혹은 실행 함수라고 불러요.)를 받아요.
        // 이 실행자는 비동기 작업이 끝나면 바로 두 가지 콜백 중 하나를 실행합니다.
        // resolve: 작업이 성공한 경우 호출할 콜백
        // reject: 작업이 실패한 경우 호출할 콜백
        const promise = new Promise((resolve, reject) => {
        	if(...){
        		...
        		resolve("성공!");
        	}else{
        		...
        		reject("실패!");
        	}
        });
        ```

    2. 프라미스의 상태값
        - pending: 비동기 처리 수행 전(resolve, reject가 아직 호출되지 않음)
        - fulfilled: 수행 성공(resolve가 호출된 상태)
        - rejected: 수행 실패(reject가 호출된 상태)
        - settled: 성공 or 실패(resolve나 reject가 호출된 상태)
        - 
    3. 프라미스 후속 처리 메서드
        - 프라미스로 구현된 비동기 함수는 프라미스 객체를 반환하죠!
        - 프라미스로 구현된 비동기 함수를 호출하는 측에서는 이 프라미스 객체의 후속 처리 메서드를 통해 비동기 처리 결과(성공 결과나 에러메시지)를 받아서 처리해야 합니다.
        - .then(성공 시, 실패 시)

            then의 첫 인자는 성공 시 실행, 두번째 인자는 실패 시 실행됩니다. (첫 번째 인자만 넘겨도 됩니다!)

            ```jsx
            // 프라미스를 하나 만들어 봅시다!
            let promise = new Promise((resolve, reject) => {
            	setTimeout(() => resolve("완료!"), 1000);
            });

            // resolve
            promise.then(result => {
            	console.log(result); // 완료!가 콘솔에 찍힐거예요.
            }, error => {
            	console.log(error); // 실행되지 않습니다.
            });
            ```

            ```jsx
            // 프라미스를 하나 만들어 봅시다!
            let promise = new Promise((resolve, reject) => {
            	setTimeout(() => reject(new Error("오류!")), 1000);
            });

            // reject
            promise.then(result => {
            	console.log(result); // 실행되지 않습니다.
            }, error => {
            	console.log(error); // Error: 오류!가 찍힐거예요.
            });
            ```

        - .catch(실패 시)

            ```jsx
            // 프라미스를 하나 만들어 봅시다!
            let promise = new Promise((resolve, reject) => {
            	setTimeout(() => reject(new Error("오류!"), 1000);
            });

            promise.catch((error) => {console.log(error};);
            ```

- 5) promise chaining(프라미스 체이닝)
    1. 프라미스는 후속 처리 메서드를 체이닝해서 여러 개의 프라미스를 연결할 수 있습니다! (이걸로 콜백 헬을 해결할 수 있어요!)
        - 체이닝이 뭔데? 그걸 어떻게 하는 건데?

            후속 처리 메서드 (then)을 쭉쭉 이어 주는 거예요.

            ```jsx
            new Promise((resolve, reject) => {
            	setTimeout(() => resolve("promise 1"), 1000);
            }).then((result) => { // 후속 처리 메서드 하나를 쓰고,
            	console.log(result); // promise 1
            	return "promise 2";
            }).then((result) => { // 이렇게 연달아 then을 써서 이어주는 거예요.
            	console.log(result);
            	return "promise 3";
            }).then(...);
            ```

- 6) async, await

    앞으로 정말정말 많이 보고 쓸 문법입니다. 
    프라미스 사용을 엄청 편하게 만들어줘요! 🙂
    **[더 알면 좋은 내용]**
    강의에서 다루지 않지만 `제네레이터`라는 함수와 `이터러블`을 알면 더더 좋습니다. 

    1. async
        - 함수 앞에 async를 붙여서 사용합니다.
        - 항상 프라미스를 반환합니다. (프라미스가 아닌 값이라도, 프라미스로 감싸서 반환해줘요!)

        ```jsx
        // async는 function 앞에 써줍니다.
        async function myFunc() {
        	return "프라미스를 반환해요!"; // 프라미스가 아닌 걸 반환해볼게요!
        }

        myFunc().then(result => {console.log(result)}); // 콘솔로 확인해봅시다!
        ```

    2. await
        - async의 짝꿍이에요. (async 없이는 못씁니다!)
        - async 함수 안에서만 동작합니다.
        - await는 프라미스가 처리될 때까지 기다렸다가 그 이후에 결과를 반환해요!

        ```jsx
        async function myFunc(){
        	let promise = new Promise((resolve, reject) => {
        		setTimeout(() => resolve("완료!"), 1000);
        	});

            console.log(promise);

        	let result = await promise; // 여기서 기다리자!하고 신호를 줍니다.

            console.log(promise);

        	console.log(result); // then(후처리 함수)를 쓰지 않았는데도, 1초 후에 완료!가 콘솔에 찍힐거예요.
        }
        ```

        await를 만나면, 실행이 잠시 중단되었다가 프라미스 처리 후에 실행을 재개합니다!
        즉, await를 쓰면 함수 실행을 기다리게 하는거예요.

---

### 참고

싱글쓰레드

[비동기](https://www.notion.so/910201490bbb42ecb2cf7909c78bf45b)