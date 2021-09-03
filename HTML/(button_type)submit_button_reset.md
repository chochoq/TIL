# (button type) submit / button / reset


# `<button type=""/>`

`button`은 3가지 type을`(submit, reset, button)` 지정해 줄 수 있다. 기본값은 `submit`.

## submit

- 해당 버튼이 폼 데이터(form data)를 제출하는 제출 버튼(submit button)임을 명시한다.
- `form`을 `submit`하면 브라우저는 페이지를 새로고침 하도록 되어있다.
이를 막기위해 `e.preventDefault();`를 사용한다.

## button

- 해당 버튼이 클릭할 수 있는 버튼(clickable button)임을 명시한다.
- `<button type="button">`을 써도 되지만, `<button>`을 쓰는 것이 권장된다.

## reset

- 해당 버튼이 폼 데이터를 초기값으로 리셋하는 리셋 버튼(reset button)임을 명시함.