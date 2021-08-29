# (HTML) input에서 유효성검사

날짜: 2021년 8월 27일

# required

- input 태그의 required 속성은 폼 데이터(form data)가 서버로 제출되기 전에 반드시 채워져 있어야 함을 확인 시킬 수 있다.

    ![](https://persistent-fruit-85b.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F1c76b717-9281-4082-81fc-62919e8f5821%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2021-08-30_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_1.26.49.png?table=block&id=dd305128-d3c3-4a40-bcc1-a2d158286160&spaceId=a07b9679-e55c-4b34-ad51-a4e7fac6c83a&width=850&userId=&cache=v2)

    ```jsx
    <form action="/examples/media/action_target.php" method="get">
        이름 : <input type="text" name="st_name" required><br>
        학과 : <input type="text" name="department"><br>
        <input type="submit">
    </form>
    ```

- required 속성이 제대로 동작하는 input 요소의 type 속성값은 다음과 같다.
    1. checkbox, date, email, file, number, password, pickers, radio, search, tel, text, url
- required 속성은 불리언(boolean) 속성이다.

    boolean 속성은 해당 속성을 명시하지 않으면 속성값이 자동으로 false 값을 가지게 되며, 명시하면 자동으로 true 값을 가지게 된다.

---

# maxlength

input 태그의 maxlength 속성은 input 요소에 입력할 수 있는 최대 문자수를 명시하고, 명시한 숫자 이상의 입력을 막아준다.

```jsx
<form action="/examples/media/action_target.php" method="get">
    이름 : <input type="text" name="st_name" maxlength="8"><br>
    학번 : <input type="text" name="st_id" maxlength="12"><br>
    <input type="submit">
</form>
```

- 반대로 minlength가 존재하며, 최소 문자 수 이상을 입력해야한다. 사용법은 maxlength와 같다.