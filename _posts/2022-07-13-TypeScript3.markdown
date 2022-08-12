---
layout: post
title: TypeScript에서 사용하는 Type
date: 2022-07-13 17:30:00 +0900
categories: TypeScript
---
### TypeScript에서 사용하는 Type
JavaScript에서 사용하는 원시타입(primitive types)들은 TypeScript에도 모두 있다.
>string    
>number    
>boolean    
>null    
>undefined    
그런데 TypeScript의 사용 목적에 비춰서 생각해보면 null이나 undefined는 굳이 사용할 이유가 없다. Type을 엄격하게 지정해서 오류를 방지하기 위해 TypeScript를 쓰기 때문에, 아예 변수 선언이 되지 않아서 반환되는 null이나 선언해놓고 값을 입력하지 않아서 등장하는 undefined를 볼 이유가 없다. tsconfig.json에서도 옵션이 있었기 때문에 혹시라도 써야 할 일이 있다면 tsconfig.json부터 시작해서 많은 부분을 건드려야 한다.

TypeScript에서 추가로 사용하는 Type들도 있다.
>union    
>any    
>unknown    
이 타입들은 TypeScript에서 Type을 조금 더 편리하게 관리하기 위해서 사용하는 Type들이다.

#### Type 지정하는 방법
원시타입 입력
> let 변수명: 타입 = 입력할 값(타입이 문자면 문자열, 숫자면 숫자)

배열에 타입 지정
> let 변수명: 타입[] = ['타입과 일치하는 값',...]
두 개 이상의 타입을 동시에 넣어야 할 경우
> let 변수명: (타입1 | 타입2)[] = ['타입1과 일치하는 값', '타입2와 일치하는 값',...]

객체에 타입 지정
> let pokemon : {키1 : 타입, 키2: 타입, ...} = {키1 : 값, 키2 : 값, ...}

내용을 참고해서 예제를 만들었다.

```TypeScript
let 이름:string = 'Bulbarsaur';
//이름 = 123; 컴파일할 때 오류가 뜬다.
let 번호:number = 1;

let 이상해풀:string[] = ['002','Ivysaur'];

let 이상해꽃: {index: number, name: string, evolve: boolean
  } = { 
    index: 3, name: 'Venusaur', evolve: false
}
```

#### Union Type
변수에 두가지 Type을 같이 사용해야 할 경우, | 연산자를 통해 변수에 들어갈 타입을 묶어서 지정할 수 있다. 이렇게 두 개의 타입을 묶어서 사용하는 Type을 Union 타입이라고 한다.

```TypeScript
let 포켓몬: number | string = 'Charmeleon';
let 포켓몬2: (number | string) = 5;
// 둘을 묶어야 할 경우
let 포켓몬3: (number | string)[] = [6, 'Charizard'];
// 이렇게 하면 number 또는 '문자열만 들어가는 배열'이 된다.
let 포켓몬4: number | string[] = ['7', 'Squirtle'];
```

#### Any Type
어떤 자료 형태도 할당 가능한 타입이다. 타입 관련 에러를 막기 위해 typescript를 쓴다는 사실을 생각해보면 any type 남용은 typescript를 쓰는 이유를 스스로 없애버리는 셈이다. 버그 체크 등 반드시 필요한 경우를 제외하고는 쓰지 말아야 한다.

#### Unknown Type
any와 마찬가지로 모든 타입의 변수를 다 할당할 수 있는 unknown 타입이 있다. any와 다른 점은 unknown type은 어떤 자료가 들어가도 그대로 타입이 unknown이다.

```TypeScript
let 포켓몬: number | string = 'Bulbarsaur';
let 포켓몬2: (number | string) = 2;

let 포켓몬3: any = 'Venusaur';
//오류 안남
포켓몬3 = 3;

let 포켓몬4: unknown = 4;
//오류 남
포켓몬4 + 1;
```