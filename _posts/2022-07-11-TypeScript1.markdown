---
layout: post
title: TypeScript Part 1-1
date: 2022-07-11 16:30:00 +0900
category: TypeScript
---
### TypeScript를 쓰는 이유
```JavaScript
console.log('5' + 2)
console.log('5' * 2)
```
> 52    
> 10    
JS는 Type이 다른데 알아서 계산을 해준다(Dynamic Typing). 여러명이 작업하면 이런 실수를 하거나 혹은 의도하지 않은 결과값을 반환해서 오류가 발생할 수 있다. TypeScript는 Type을 엄격하게 확인해서 의도하지 않은 오류를 막아준다. 그 외에 객체 지향 프로그래밍에 조금 더 적합하게 튜닝이 되어 있다는데 이건 지금은 체감 못하는 중.

### TypeScript 설치
Nodejs 설치되어 있는지 확인한 뒤 터미널에서
> npm install -g typescript    
<details>
<summary>오류날 경우</summary>
nodejs 업데이트    
windows : powershell 관리자 권한으로 실행한 뒤 set-ExecutionPolicy Unrestricted 입력 → y    
mac : sudo 붙여서 실행    
</details>

설치 끝나면 TypeScript로 작업할 폴더로 이동해서 tsconfig.json 파일 생성해서 TypeScript를 JavaScript로 컴파일할때 설정을 작성. 그 다음에 작업하면 됨. 파일 확장자는 .ts

TypeScript 파일은 nodejs에서 바로 실행되지 않음. 따라서 JS로 변환이 필요. 터미널에서 tsc -w 실행하면 자동 변환됨.

#### React에 적용
<details>
<summary>React 프로젝트에 적용</summary>
작업 폴더에서 터미널 열고
npm install --save typescript @types/node @types/react @types/react-dom @types jest
입력
</details>

<details>
<summary>새로운 React 프로젝트 생성</summary>
프로젝트를 생성할 작업 폴더에서 터미널 열고
npx create-react-app my-app --template typescript
입력
</details>

#### Vue에 적용
작업 폴더에서 터미널 열고
vue add typescript
입력

vue 파일에서 타입스크립트 활용하려면
> <script lang="ts">    
> </script>    

### tsconfig.json
TypeScript 파일을 JavaScript로 변환할 때 어떻게 변환할 것인지 세부설정을 담은 파일

```TypeScript
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
    }
}
```