---
layout: post
title: TypeScript Part 2-1
date: 2022-07-18 17:10:00 +0900
categories: TypeScript
---
> 코딩애플 빠르게 마스터하는 TypsScript 강의 학습
# Class
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