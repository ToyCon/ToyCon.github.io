---
layout: post
title: TypeScript Part 1-3
date: 2022-07-13 17:30:00 +0900
categories: TypeScript
---
### JavaScript의 Type
원시 타입(primitive type)
number
string
boolean
undefined
null
symbol
객체 타입(object / reference type)
객체, 함수, 배열 등

> TypeScript의 Types
primitive types
string
number
boolean
null
undefined
> null undefined는 굳이 사용하지 않음
굳이 타입을 지정할 필요가 없음. 변수를 선언할 때 변수형에 맞춰서 입력하면 자동으로 타입 지정됨

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