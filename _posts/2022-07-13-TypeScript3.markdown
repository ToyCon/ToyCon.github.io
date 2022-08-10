---
layout: post
title: TypeScript Part 1-3
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

내용들을 참고해서 예제를 만들어 실험해봤다.

```TypeScript
let 이름:string = 'Bulbarsaur';
//이름 = 123; 오류납니다

let 배열:string[] = ['Bulbarsaur','Ivysaur'];
let 번호:{indexnum : number} = {indexnum = number};

type nameType = string | number;
let 이름:nameType = 'Venusaur';

function 함수명(x:number) : number {
    return x*2;
}

//에러가 발생하는 함수
/*function 함수명(x:number | string) {
    return x*2;
}*/
//이건 가능
function 함수2(x: nbumber | string) {
    if(typeof x === 'number'){
        return x * 2;
    }
}

type pokemon = [number, boolean];
let bulbarsaur:pokemon = [001, true];
```

> 함수에 타입 지정하기

> Union Type
| 연산자를 사용해서 두 가지 type을 지정할 수 있음
any type : 어떤 자료 형태도 할당 가능. 하지만 타입 관련 에러를 막기 위해 typescript를 쓰기 때문에 남발하면 typescript 쓰는 이유가 사라짐
unknown : any와 마찬가지로 모든 타입의 변수를 다 할당할 수 있음. 차이점은 unknown type은 어떤 자료가 들어가도 그대로 타입이 unknown임

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

> 타입 확정하기


> Type 키워드
> readonly
# Narrowing & Assertion
| 연산자를 사용해서 두 가지 type을 지정할 수 있음
any type : 어떤 자료 형태도 할당 가능. 하지만 타입 관련 에러를 막기 위해 typescript를 쓰기 때문에 남발하면 typescript 쓰는 이유가 사라짐
unknown : any와 마찬가지로 모든 타입의 변수를 다 할당할 수 있음. 차이점은 unknown type은 어떤 자료가 들어가도 그대로 타입이 unknown임

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