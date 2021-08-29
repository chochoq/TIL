# github page로 호스팅하기

날짜: 2021년 8월 17일
속성: 2021년 8월 25일 오후 7:30
태그: github

# github web에서 작업하기

1. 해당 repository → 설정 → pages

    ![ ](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F94edc7c2-9066-4544-894d-9b9368b657c2%2F_2021-05-17__4.36.29.png?table=block&id=04e12fb8-cc69-4651-869a-ab461a02ad3a&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=4920&userId=&cache=v2)

2. 사용할 브랜치 설정하기

    ![](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fde4aac57-0b08-4f86-b9e4-f59b3c18b537%2F_2021-05-17__4.40.02.png?table=block&id=0812132b-bec6-452d-baf8-18b677286155&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=1470&userId=&cache=v2)

    ![](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F8ad93f77-9d62-4725-ae76-f83f5f661326%2F_2021-05-17__4.41.33.png?table=block&id=97afd0ec-a454-4a53-98ca-d6a162328d02&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=3260&userId=&cache=v2)


3. 주소가 생성된것을 확인할수있다

    ![](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F12ab06de-c022-4da4-9bcf-21c01b5ddba8%2F_2021-05-17__4.43.40.png?table=block&id=06936659-fecc-4a9d-95e6-458c99c4fae1&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=2320&userId=&cache=v2)


4. code로 돌아가서 작성한 코드를 업로드합니다.
(작성한 코드가 있기때문에 저는 아래의 upload files로 하겟습니다)

    ![](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fa554c246-9bb4-40d5-8204-abf9ee742d7c%2F_2021-05-17__4.45.14.png?table=block&id=bed66d4e-7930-4a69-a1f2-2f88909d4548&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=1600&userId=&cache=v2)

5. 페이지로 만들어준 파일들을 모두 업로드해줍니다.

    처음에 보여질 메인페이지의 이름은 반드시 index.html이여야 합니다.

    ![](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb6c988fe-5256-4e36-96e2-e203d5e96384%2F_2021-05-17__4.49.42.png?table=block&id=55485352-6c4d-4cb0-84f7-e6e42d7656f0&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=3290&userId=&cache=v2)

6. 아까 확인했던 페이지주소로 들어가면 완료!
주소로 들어갔을때 리드미 페이지가 뜨거나, 혹은 [https://chochoq.github.io/pageTest/index.html](https://chochoq.github.io/pageTest/index.html)로 해야지 들어가는 경우가있다.
시간이 조금 걸리는 경우이니 조금만 기다려보자

    완성~

    ![](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fe2b39e25-eda2-4ff5-8063-0cd0dbdacc31%2F_2021-05-17__8.12.30.png?table=block&id=233d94d0-c21a-4abf-bf57-91c9e95354d7&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=2560&userId=&cache=v2)

---

# vsc에서 작업하기

1. `npm i gh-pages` Install

    zsh창에서 명령어를 넣어야 작동한다.

    ![스크린샷 2021-08-26 오전 1.57.39.png](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fe48e4519-8e25-4715-b0d0-8a2506976bfe%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-26_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_1.57.39.png?table=block&id=4a2c27c3-54de-405e-abf8-b4bb9397b35c&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=580&userId=&cache=v2)

2. package.json로 들어가준다.
    - 아래쪽에 homepage url을 적어준다.

        ```jsx
        "homepage": "github page로 사용할 url"
        ```

    - scripts에 아래 명령어를 추가한다.

        ```jsx
        "scripts": {
            "start": "react-scripts start",
            "build": "react-scripts build",
            "test": "react-scripts test",
            "eject": "react-scripts eject",
            "deploy": "gh-pages -d build",
            "predeploy": "npm run build"
          },
        ```

3. `npm run build`로 빌드를 해준다.
4. url에 호스팅이 완료가 됐는지 확인한다.

vscode로 작업하면 수정 후 빌드할 때 자동으로 페이지에 업로드되서 편하다.