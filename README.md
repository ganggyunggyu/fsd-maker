# FSD 메이커 스크립트

### 설치 방법

FSD 생성 스크립트를 실행하려면, 터미널에서 아래 명령어를 입력해 주세요!

### 의존성 설치

먼저 필요한 의존성을 설치해야 합니다. 터미널에서 아래 명령어를 실행해 주세요:

```bash
yarn add -D typescript ts-node @types/node @types/fs-extra
yarn add fs-extra commander
```

package.json에 스크립트 추가
package.json 파일에 스크립트를 추가해 주세요. 이렇게 하면 명령어를 더 간편하게 사용할 수 있습니다.

```
{
  "scripts": {
    "fsd-g": "ts-node fsd-maker.ts generate-fsd"
  }
}
```

### 사용법

설치가 끝난 후, 이제 fsd-g 명령어를 실행할 준비가 되었습니다! 터미널에서 아래와 같이 명령어를 실행해 주세요:

```bash
yarn fsd-g <depth> <domain>
npm run fsd-g <depth> <domain>
```

### 예시

만약 feature라는 깊이와 user라는 도메인에 대해 폴더 구조를 생성하고 싶다면, 아래와 같이 입력합니다.

```bash
yarn fsd-g feature user
```

### 생성되는 폴더 구조

명령어를 실행하면, 아래와 같은 폴더 구조가 자동으로 생성됩니다.

```
src/
  feature/
    user/
      api/
        index.ts
        user.api.ts
      ui/
        index.ts
      hooks/
        index.ts
        user.hooks.ts
      model/
        index.ts
        user.model.ts
      index.ts
```

### 각 폴더의 역할

api: API 관련 로직이 들어갑니다. user.api.ts 같은 파일이 생성됩니다.

ui: UI 컴포넌트와 관련된 파일이 들어갑니다.

hooks: 리액트 훅스와 관련된 로직을 담습니다.

model: 데이터 모델과 관련된 로직을 담습니다.

index.ts: 해당 도메인에 대한 모든 항목들을 내보내는 파일입니다.

### 주의 사항

<depth>는 폴더의 깊이를 지정하는 부분입니다. 예를 들어, feature나 entities와 같은 값이 들어갑니다.

<domain>은 생성할 도메인의 이름입니다. 예시에서는 user와 같은 도메인 이름이 들어갑니다.
