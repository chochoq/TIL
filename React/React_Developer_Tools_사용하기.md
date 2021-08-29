# React Developer Tools 사용하기

Chrome용 React.js의 오픈소스 React 개발자도구이다.

devTools에서 React 구성요소 계층구조를 확인할 수 있다.

"⚛️Components"와  "⚛️Profiler" tap을 확인 할 수 있다.

1. [크롬 익스텐션](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)으로 설치를 합니다.
2. 설치 후 개발자 툴(F12)에서 확인이 가능합니다.(react로 개발 된 웹에서만 활성화 됨을 확인할 수 있다.)

    ![스크린샷 2021-08-29 오후 11.06.54.png](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F5ce9255d-c5c5-47af-9193-2102216967d2%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-29_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.06.54.png?table=block&id=50c2951c-224b-4610-8203-b105c1a4313c&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=990&userId=&cache=v2)

    ![스크린샷 2021-08-29 오후 11.09.14.png](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fe6a9865f-3dfc-4de2-8085-33eb3cc94f8f%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-29_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_11.09.14.png?table=block&id=fd6792ad-6048-420c-b7a7-fd20b75cef18&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=1960&userId=&cache=v2)

- ⚛️Components⚛️
    1. 렌더링 된 루트 구성요소와 렌더링을 끝낸 하위 구성요소가 표시된다.
    2. 트리에서 구송요소 중 하나를 선택해 props 와 state를 검사하고 편집할 수 있다.
    3. 이동경로에서 선택한 구성요소, 구성요소를 만든 구송요소 해당 구성 요소를 만든 구성요소등을 검사할 수 있다.
    4. 일반 Elements 탭을 사용하여 페이지의 React 요소를 검사한 다음 React 탭으로 전환하면 해당 요소가 React 트리에서 자동으로 선택된다.
- ⚛️Profiler⚛️
    1. 성능 정보를 기록할 수 있다.

---

## React의 렌더링 시점

- state가 변경될 때
- props가 변경될 때
- 부모 컴포넌트가 변경될 때
- forceUpdate()가 호출 될 때

---

[소스코드](https://github.com/facebook/react/tree/master/packages/react-devtools-extensions)