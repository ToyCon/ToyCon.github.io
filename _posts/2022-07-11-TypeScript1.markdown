---
layout: post
title: TypeScript Part 1-1
date: 2022-07-11 16:30:00 +0900
category: TypeScript
---
> 코딩애플 빠르게 마스터하는 TypsScript 강의 학습
# TypeScript의 Types
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