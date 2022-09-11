# Team Palette Challenges Repo

멋쟁이 사자처럼 프론트엔드 스쿨 3기에서 만난 🎨 `Palette`의 Code Review를 위한 repo입니다.

# 처음 시작하는 팀원을 위한 설명서

`원격 저장소`(='remote 레포지토리')는 클라우드(여기에선 Github)에 올라간 저장소를 의미합니다.

저희는 이 원격 저장소를 각자가 연결해 '협업'을 해야 합니다.

아래의 스텝을 따라 환경을 구성해주세요.

## 0. VSC Extension 설치 (선택사항)

- `Git Graph`: VSC에서 Git의 브랜치 변경 내역을 편리하게 확인할 수 있도록 도와줍니다.

## 1. 현재 레포지토리를 Fork하기

![fork](./images/README/fork.png)

`fork`를 누릅니다.

![create-fork](./images/README/create_fork.png)

`Create Fork`를 누릅니다.

![forked](./images/README/forked.png)

`<본인의 깃헙 닉네임>/FE-School-Challenges` 라는 이름의 원격 저장소가 생성됐다면 포크가 잘 된 것입니다.

> 포크는 다른 사람의 원격 저장소를 복사해서 '내 계정 버전의' 원격 저장소를 만드는 기능입니다. 앞으로 방금 '포크를 뜬' 원격 저장소에 push하는 내용은 오로지 내 레포지토리에만 올라갑니다.

## 2. Fork한 레포지토리를 로컬에 clone하기

![clone](./images/README/clone.png)

방금 포크한 저장소에서 `Code`를 눌러 원격 저장소의 URL을 복사한 후, 아래의 명령어를 터미널에 입력합니다.

```console
cd 클론한/저장소가/위치할/경로로/이동
git clone <방금_복사한_URL>
```

> 클론은 원격 저장소를 '복사'해서 로컬에 다운로드 받는 것을 의미합니다. 저장소 자체를 복사하기 때문에 `.git`이 자동으로 생성됩니다.

아래 명령어를 입력해서 제대로 연결됐는지 확인해보세요. `origin`이라는 이름의 원격 저장소가 본인의 원격 저장소 URL로 연결돼있으면 됩니다.

```console
git remote -v
```

## 3. 원본 저장소 연결하기

협업을 통해 원본 저장소에 코드들이 올라왔다고 생각해보면, 변경된 내용을 로컬로도 가지고 올 수 있어야 합니다. 아래 명령어를 입력해서 원본 저장소와도 연결해줍니다.

```console
git remote add upstream https://github.com/LikeLion-Palette/FE-School-Challenges.git
# 원본 원격 저장소를 'upstream'이라는 이름으로 로컬 저장소에 추가합니다.
```

입력했다면 아래 명령어로 제대로 연결됐는지 확인합니다. `upstream`이라는 이름으로 원본 저장소가 연결돼있으면 됩니다.

```console
git remote -v
```

현 상태에서 저장소는 아래의 세가지가 있습니다.

- 로컬 저장소: 포크 뜬 저장소를 내 컴퓨터로 `clone`한 저장소
- 포크 뜬 저장소(로컬 저장소 입장에서는 `origin`): `<깃헙_닉네임>/FE-School-Challenges`
- 원본 저장소(로컬 저장소 입장에서는 `upstream`): `LikeLion-Palette/FE-School-Challenges`

협업 전략은 아래와 같습니다. (우선은 흐름을 알아두세요!!)

1. 로컬에 변경을 `commit`
2. 로컬에서 `origin`으로 `push`
3. `upstream`에 반영하기
  1. PR하기 전에, `upstream`에 바뀐 내용이 없는 경우: `origin`에서 `upstream`으로 PR(Pull Request)
  2. PR하기 전에, `upstream`에 바뀐 내용이 있는 경우
    1. `upstream`에서 로컬로 `pull`
    2. 로컬에서 `origin`으로 `push`
    3. `origin`에서 `upstream`으로 PR

> Pull Request, PR이란 원본 저장소에 '내가 변경한 내용을 보고 맘에 들면 합쳐(merge)줘!' 라고 요청하는 행위입니다.

### 3-0. Git pull 설정

저희가 사용할 git pull 전략은 `rebase`를 사용하지 않고 단순 `merge`를 하는 방식입니다. (자세한건 알잘딱깔센 참고)

아래 명령어를 입력해 설정해주세요.

```console
git config pull.rebase false
```

### 3-1. 원본 저장소로부터 코드 가져오기

이 단계는 앞으로 본인의 코드를 작성하거나 올리기 전에 꼭 해줘야 충돌이 일어나지 않습니다.

```console
git pull upstream main
# upstream 저장소의 main 브랜치로부터 바뀐 내용을 가져오겠다는 의미입니다.
```

원본 저장소와 차이가 있는 부분이 있을 경우 몇 개의 파일이 얼마나 바뀌었는지 출력되고, 그렇지 않은 경우엔 'Already up to date.'가 출력됩니다.

**__꼭 본인의 코드를 올리기 전에 이 단계를 먼저 수행해주세요!__**

## 4. `issue` 확인하고 과제를 위한 브랜치 생성하기

[원본 레포지토리의 `issues` 탭](https://github.com/LikeLion-Palette/FE-School-Challenges/issues)에 들어가보시면 과제가 열려있습니다.

![issue](./images/README/issue.png)

앞으로 조장이 과제가 생길때마다 이렇게 issues를 오픈하겠습니다. 참고해 브랜치를 생성해주시면 됩니다.

> 원래 `issue`는 협업시 개발이 필요한 내용을 말 그대로 '이슈 제기'하는 곳입니다. 예를 들어 버튼 개발이 필요하다면 '버튼 개발하기' 라는 이름의 이슈를 열고, 관련 내용을 적는 것입니다. 이렇게 함으로써 프로젝트를 위해 앞으로 어떤 것들을 해결해 나가야 하는지 쉽게 알 수 있습니다.

<img src="./images/README/create_branch_by_issue.png" width="250px" />

과제 이슈를 클릭해 **우측에 위치한** `Create a branch`를 클릭해주세요.

![create_branch](./images/README/create_branch.png)

`Repository destination`이 `<본인 깃헙 닉네임>/FE-School-Challenges`가 맞는지 확인해주세요. **과제를 위한 브랜치를 아까 포크떴던 레포지토리에 자동 생성**하는겁니다.

> 깃헙은 이런식으로 이슈를 열면 그 이슈와 관련된 작업을 할 수 있도록 브랜치를 편리하게 생성해줍니다. 참고로 여기서 생성되는 브랜치의 이름은 issue 이름으로 자동으로 설정되고, 맨 앞에 붙는 숫자(예시에서는 2)는 issue 번호를 의미합니다.

확인이 됐다면 `Create branch`를 클릭해주세요.

## 5. 원격에 생성된 과제용 브랜치를 로컬로 받아오기

여기까지 했다면 지금은 '포크떴던 저장소에는 과제용 브랜치가 생성됐지만, 로컬 환경에는 반영이 안된 상태' 입니다. 아래 명령어를 통해 확인해보세요.

```console
git branch -r
# 원격 저장소들에 있는 브랜치들을 모두 볼 수 있습니다.

git branch
# 현재 로컬에 있는 브랜치들을 모두 볼 수 있습니다.
```

origin에 생성된 과제용 브랜치를 로컬로 가져오려면 `git checkout` 명령어를 사용해야 합니다.

```console
git checkout -t origin/2-2주차-버킷리스트-만들기
```