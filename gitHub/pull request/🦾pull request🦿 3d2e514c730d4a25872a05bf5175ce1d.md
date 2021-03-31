# 🦾pull request🦿

속성: 2021년 3월 19일 오전 10:57
태그: git, github

# Fork? Clone?

- **fork**

    원격저장소(리포지토리)를 내 것으로 가져온다. 수정을 해도 원래의 repo에는 지장이 없으므로 걱정없이 사용이 가능합니다.

- **clone**

    같은 repo를 사용하기때문에 수정을하면 원본의 repo에도 같이 수정이 됩니다.

# what's pull request?

- 작업한 코드를 repository에 merge 하기 전 merge가 이루어져도 좋은 지 코드의 관리자들이나 팀원들에게 리뷰 받는것
- 특정 개인이 마음대로 코드 저장소를 수정할 수 없게 하는 것

# pull requests  good thing

- 중요한 branch 보호(master branch)해 협의없이는 변경할 수 없게 만들어 준다.
- 코드의 변경이 이루어져도 좋은지 함께 살펴보면서 코드리뷰가 이루어진다.

    → 자연스럽게 학습에도 좋은 영향을 끼치다.

    → 다른사람에게 보여준다는 생각을 가지고 개발하게되면 코드에 품질에 신경쓰게된다.

이 게시글에서 모든 pull requests는 깃허브 웹페이지로 진행됩니다.

# 브랜치 보호정책

![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__12.38.51.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__12.38.51.png)

1. 레포지토리의 **settings** 클릭
2. **branches** 클릭
3. **add rule** 클릭
4. **branch name pattern →** 몸통브랜치가 되는 브랜치를 확인하고 써주세요 main or marster
    - 리뷰를 몆명에게 받아야하는지 체크하고 설정된 인원수의 사람에게 코드리뷰를 받아야지 merge할수있습니다
    - 이 적용사항이 레포지토리의 주인에게도 적용되게 설정합니다.

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__12.47.47.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__12.47.47.png)

5. 이와같이 설정을 했다면 앞으로 우리는 main or marster 브랜치에 곧바로 commit이 불가능해집니다. 그럼 다음에 우리가 해야할 것은?

# pull request routine

### 당신이 커밋을 했다면

1. 새로운 브랜치를 딴후 커밋과 푸쉬를 해줍니다
(아직 숙달되지않았기 때문에 커밋마다 새로운 브랜치를 따봅니다)
2. github로 돌아와 푸쉬한 사항을 풀리퀘스트 요청해줍니다.

    아래의 사진에서 머지시키길 원하는 브랜치를 선택,확인 해줍니다(보통 main or master)

    메세지를 적어주고 풀리퀘스트 요청을 해줍니다.

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__8.06.22.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__8.06.22.png)

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__8.09.25.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__8.09.25.png)

3. 요청을 완료 했다면 아래 빨간색으로 무섭게 경고가 표시되있습니다.

    하지만 don't worry 

    review required → 검토가 필요합니다

    merging is blocked → 머지(병합)이 차단되었습니다.

    브랜치 보호정책 설정을 했기 때문입니다.

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.23.09.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.23.09.png)

4. repo를 같이 사용하는 Contributor의 리뷰를 기다립니다.

### 당신이 리뷰를 작성해야 한다면

1. repo의 메뉴바에 보면 pull requests가 보입니다.

    그 옆에 숫자가 보이나요?
    이 의미는 pull requests가 3개가 있다는 의미입니다. 

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.29.26.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.29.26.png)

2. 리뷰를 작성할 2개의 풀리퀘가 보입니다.
그럼 하나의 풀리퀘 요청에 들어가 보겟습니다.

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.34.34.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.34.34.png)

3. 리뷰어의 요청을 기다리고 있는 것이 보입니다.

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.38.08.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.38.08.png)

4. 1 → 커밋 메뉴로 들어가 바뀌거나 추가된것을 확인합니다
2 → review changes(변경사항검토) 버튼클릭

    3 → 작성할 코멘트를 써주세요

    4 → 커밋한 코드가 마음에 들었다면(?) approve를 선택하고 submit을 해줍니다.
    하지만, 작성한 코드가 마음에 들지않았다면 comment를 작성해 왜 이딴 코드를 만들었냐고 따져줍니다. 이때 Request changes를 선택해 변경요청을 해줄수도있습니다 

    하지만 저는 무조건 마음에 듭니다. 저에게 트러블이란 없기때문에!!!111

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.40.07.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.40.07.png)

    5. 충돌이 없기 때문에 바로 메인 브랜치에 merge(병합) 시킬수있습니다.

    thanks god👌 (개발을 하다보니 어느새 모든 신을 믿고있는 저를 발견했습니다)
    아래 머지 메세지를 작성하고 성공한 메세지를 볼수있습니다.
    저는 깔끔한 브랜치를 위해 delete branch 클릭. 지워도 되돌리기(revert) 가능합니다.

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.59.40.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__6.59.40.png)

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__7.05.50.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__7.05.50.png)

    6. 완료가 되어 Create hoho 가 보이지 않는 것을 확인할 수 있습니다.
    code에서도 확인이 가능합니다

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__7.09.41.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__7.09.41.png)

    ![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__7.11.12.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__7.11.12.png)

# 4. 로 다시 돌아가 코드리뷰를 해보겟습니다.

![%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__8.13.43.png](%F0%9F%A6%BEpull%20request%F0%9F%A6%BF%203d2e514c730d4a25872a05bf5175ce1d/_2021-03-19__8.13.43.png)

- 1의 경우는 comment 선택을 하고 의견을 제시했습니다.
- 2의 경우는 request changes(변경요청)을 하면서 코멘트를 달았습니다.

    이 경우 변경을 할경우 다시 사용하던 ide로 돌아가 새로 커밋을 해줍니다.
    요청을 했지만 문제가 없고 머지를 시켜도 될 경우 4로 다시 돌아가 approve 후 submit을 해주면 됩니다.