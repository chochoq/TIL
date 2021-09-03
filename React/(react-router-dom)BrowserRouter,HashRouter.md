# (react-router-dom) BrowserRouter, HashRouter

날짜: 2021년 8월 24일

react-router-dom에서 사용하는 라우터는 보통 다음과 같다.

- <BrowserRouter>
- <HashRouter>
- <MemoryRouter>
- <NativeRouter>
- <StaticRouter>

# HashRouter

### HashRouter의 특징

- 주소창에 #(hash)가 붙는다.
- seo가 안된다(검색엔진이 읽지 못한다.)
- URL Hash를 사용해 브라우저나 웹서버에 제한이 없다.
- 해시 히스토리를 지원하지 않는다.

# BrowserRouter

- github page에 설정하는 것이 까탈스럽다
- Link 컴포넌트로 to 속성에 이동할 경로를 써준다.
- 새로고침 하면 경로에서 못 찾아 에러가 난다.