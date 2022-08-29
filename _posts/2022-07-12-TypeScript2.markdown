---
layout: post
title: tsconfig.json
date: 2022-07-12 19:30:00 +0900
categories: TypeScript
---
### tsconfig.json
TypeScript 파일을 JavaScript로 변환할 때 어떻게 변환할 것인지 세부설정을 담은 파일이다.

```TypeScript
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
    }
}
```

컴파일 옵션은 무조건 들어가야 한다. 컴파일 옵션 외에도 watchOption, typeAcquisition이 들어가야 하는데 오늘은 compilerOption만 정리하고 나중에 보강할 예정이다. 전체 설정은 (https://www.typescriptlang.org/tsconfig) 여기서 볼 수 있다.

complilerOptions에 들어갈 하위 키들을 강의자료를 참고해서 정리했다.
#### 1.JS 변환 관련
> 'target': 'es3', 'es5', 'es6' / 'es2015', 'es2016', 'es2017','es2018', 'es2019', 'es2020', 'es2021', 'es2022', 'esnext' 중 1개    
> es5로 변환한 파일을 열어보면 변수 선언이 죄다 var로 되어 있다. 현재 사용되는 es6 문법에서는 사용하지 말것을 권장하는 문법이기 때문에 해도 된다 하지 말아야 한다 이런 부분을 알아보려고 검색을 해봤는데 TypeScript 홈페이지의 tsconfig 항목에서 답을 찾아볼 수 있었다. 'ES6를 지원하는 환경이면 ES6가 좋은 선택이다'라고 하니 예전 문법으로 작성해도 큰 문제는 없다고 생각한다. 아마 하위 호환을 위해 예전 문법으로도 변환할 수 있도록 기능을 살려둔게 아닐까. JS쪽에서 가능하면 ES6 이후 문법 사용을 권장하고 있으니 디폴트 값은 es6로 해야겠다.    

> 'module': 'commonjs', 'amd', 'es2015', 'esnext'    
> code 모듈화해서 내보내고 가져올 때 무슨 import 문법 쓸건지 정한다. es6에서는 모듈 시스템인 import를 사용한다고 한다. 이건 JS와 관련된 내용이라 여기에는 길게 적지 않으려고 한다. 기본값을 es6로 지정해서 사용하는 만큼 나는 es2015를 기본값으로 넣으려고 한다.    

> 'allowJs': true, false    
> js 파일을 ts에서 import해서 쓸 수 있는지 여부를 확인한다. 필요한 경우 true.    

> "checkJs": true, false    
> 일반 js 파일에서도 typescript에서 확인하는 에러를 체크하는지 설정한다. JS 파일을 불러올 경우 필요할 듯. 쓴다면 true.    

> "declaration": true, false    
> 컴파일할 때 타입을 저장하는 .d.ts 파일 생성 여부를 확인한다. 매우 편리한 기능이므로 어지간하면 true.    

> "rootDir": "./" 또는 지정된 폴더    
> 루트경로를 변경한다. 아래 옵션과 함께 JS 파일 저장 경로에 영향을 준다.    

> "outDir": "./" 또는 경로 지정    
>  컴파일한 JS파일을 저장할 경로를 변경한다. 같은 폴더안에 저장하지 않을 경우 유용할 듯.    

> "removeComments": true, false    
> JS 파일로 컴파일할 때 TS 파일에 있는 주석을 삭제할 것인지 물어본다. 실제 작동하는 JS 파일로 컴파일 할때 작동하는 파일이므로 어지간하면 true.    

#### 2. TS 문법 관련
>"strict": true, false
> Type과 관련된 기능들에 적용되는 엄격한 설정들을 모두 활성화하는 명령. strict, noImplicit 가 붙는 옵션을 모두 활성화 한다.    

>"noImplicitAny": true, false    
>any타입을 금지할 지 설정한다. any type은 디버그나 반드시 필요한 경우가 아니면 사용되지 않으므로 어지간하면 true.    

>"strictNullChecks" : true, false    
>null, undefined에 뭔가 실행할 경우 에러를 띄워준다. 변수를 하나씩 체크할 필요가 없어져서 오류 체크에 매우 유용할 듯.    

>"strictFunctionTypes": true, false    
>함수 파라미터 타입을 엄격하게 체크.    

>"strictPropertyInitialization": true, false    
> class constructor 작성시 타입체크 를 엄격하게 한다.    

>"alwaysStrict": true, false    
>컴파일하는 JS에서도 "use strict"를 적용하는지 여부.    

#### 3. 메모리 관리
>"noUnusedLocals": true, false    
>사용하지 않은 지역변수가 존재하면 에러를 출력한다.    

>"noUnusedParameters": true, false    
>사용하지 않은 파라미터가 존재하면 에러를 출력한다.    

>"noImplicitReturns": true, false    
>return이 없는 함수가 존재하면 에러를 출력한다.    

>"noFallthroughCasesInSwitch": true, false    
>switch문에 오류가 있으면 에러를 출력한다.    

### 내가 설정한 tsconfig.json
앞으로 작업할 때 기본값으로 만들어서 사용할 json 파일을 작성해둔다. 사용해보고 앞으로 계속 업데이트할 예정이다.

```TypeScript
{
    "compilerOptions": {
        "target": "es6",
        "module": "es2015",
        "declaration": true,
        "removeComments": true,
        "strict": true,
        "noUnusedLocals": true,
        "noUnusedParameters": true
    }
}
```