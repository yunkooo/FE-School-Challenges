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

> 클론은 원격 저장소를 '복사'해서 로컬에 다운로드 받는 것을 의미합니다. 저장소 자체를 복사하기 때문에 `.git`이 자동으로 생성돼 따로 설정을 해 줄 필요는 없습니다.

<!-- ## 0. 시작에 앞서 일부 용어 설명

- 원격 브랜치: 원격 저장소의 상태를 반영하는 브랜치입니다. `<remote name>/<branch name>`의 형식으로 명명됩니다. `origin/main`이라면 origin 원격 저장소의 main 브랜치를 의미합니다.

-

## 1. 로컬에 원격 저장소를 클론하기

```console
cd 클론한/저장소가/위치할/폴더로/이동
git clone
```

이렇게 하면 현재 폴더에 복사된 상태

## 2. 원격 저장소의 변경사항을 내려받기

```console
git pull
``` -->
