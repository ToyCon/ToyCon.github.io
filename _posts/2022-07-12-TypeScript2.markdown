---
layout: post
title: TypeScript Part 1-2
date: 2022-07-12 19:30:00 +0900
categories: TypeScript
---
원래 첫 번째 포스트에 몰아서 정리햇었는데 분량이 늘어나서 별도의 포스트로 분리. 

### tsconfig.json
TypeScript 파일을 JavaScript로 변환할 때 어떻게 변환할 것인지 세부설정을 담은 파일.

```TypeScript
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
    }
}
```

컴파일 옵션은 무조건 들어가야 한다. 컴파일 옵션 외에도 watchOption, typeAcquisition이 들어가야 하는데 오늘은 compilerOption만 정리하고 나중에 보강할 예정이다. 전체 설정은 (https://www.typescriptlang.org/tsconfig) 여기서 볼 수 있다.

이렇게만 작성해도 잘 변환되고 잘 실행된다. 그런데 

complilerOptions에 들어갈 하위 키들을 강의자료를 참고해서 정리했다. 전체는 여기서 볼 수 있다. 

> "target": 'es3', 'es5', 'es6' / 'es2015', 'es2016', 'es2017','es2018', 'es2019', 'es2020', 'es2021', 'es2022', 'esnext' 의 값을 가진다.
>> es5로 변환한 파일을 열어보면 변수 선언에 죄다 var로 되어 있다. 현재 사용되는 es6 문법에서는 사용하지 말것을 권장하는 문법이기 때문에 해도 된다 하지 말아야 한다 이런 부분을 알아보려고 검색을 해봤는데 TypeScript 홈페이지의 tsconfig 항목에서 찾아볼 수 있다. 'ES6를 지원하는 환경이면 ES6가 좋은 선택이다'라고 하니 예전 문법으로 작성해도 큰 문제는 없다고 생각한다. 아마 하위 호환을 위해 예전 문법으로도 변환할 수 있도록 기능을 살려둔게 아닐까. 다만 JS쪽에서 가능하면 ES6 이후 문법 사용을 권장하고 있으니 디폴트 값은 es6로 해야겠다.

"noImplicitAny" : true → any 타입이 발생할 경우 에러를 띄워준다.
"strictNullChecks" : true → null, undefined에 뭔가 실행할 경우 에러를 띄워준다.
