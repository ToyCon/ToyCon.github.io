---
title: 다항식 더하기
date: "2023-05-07T20:33:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120863"
---
### 다항식 더하기    
https://school.programmers.co.kr/learn/courses/30/lessons/120863    
    
#### 변수    
다항식 polynomial    
    
#### 제한    
0 < polynomial에 있는 수 < 100    
polynomial에 변수는 'x'만 존재    
polynomial은 0부터 9까지의 정수, 공백, ‘x’, ‘+'로 구성    
항과 연산기호 사이에는 항상 공백이 존재    
공백은 연속되지 않으며 시작이나 끝에는 공백이 없음    
하나의 항에서 변수가 숫자 앞에 오는 경우는 없음    
" + 3xx + + x7 + "와 같은 잘못된 입력은 주어지지 않음    
"012x + 001"처럼 0을 제외하고는 0으로 시작하는 수는 없음    
문자와 숫자 사이의 곱하기는 생략    
polynomial에는 일차 항과 상수항만 존재    
계수 1은 생략    
결괏값에 상수항은 마지막에 나옴    
0 < polynomial의 길이 < 50    
    
#### 풀이    
x의 동류항을 별도의 배열로 분리하여 x와 정수의 합을 반환하는 방식으로 풀었다.    
1. 변수 X 선언하고 polynomial.match(/\d*x/g) 할당    
2. X의 모든 원소의 x를 replace 0으로 변환한 뒤 결과가 '0'인 경우 '10'으로 재변환    
3. reduce 메서드 적용하여 모든 원소의 합으로 변환한 뒤 10으로 나눠줌    
4. 변수 numbers 선언하고 polynomial.split(' ') 할당    
5. numbers 배열의 모든 원소를 number 타입으로 변환하고 NaN이 아닌 원소만 남김    
6. numbers에 reduce 적용하여 모든 수의 합을 할당    
7. X의 값이 1인지 확인, 1일 경우 빈 문자열을 재할당    
8. 삼항연산자로 numbers의 값이 0인지 확인, 0일 경우 `{X}x`, 아닐 경우 `{X}x + {numbers}` 반환
    
#### 코드    
실제로 풀 때는 x동류항 또는 숫자 동류항이 없는 경우를 고려해서 중간에 배열이 맞는지 확인하는 과정을 추가하였다. x항만 존재하는 경우와, 정수항만 존재하는 경우가 따로 있어서 풀이와 코드가 많이 달라졌다. 다른 사람들의 풀이를 보니 split 메서드 연산자를 아예 ' + '로 사용해서 항만 골라내는 방식이 있었는데 좋은 방식인 것 같다. 기억하고 있어야 겠다.    
```JavaScript
function solution(polynomial) {
    let res = '0';
    let X = polynomial.match(/\d*x/g);
    let numbers = polynomial.split(' ').map(e => Number(e)).filter(e => !isNaN(e));
    if(Array.isArray(X)) {
        X = X.map(e => e.replace('x', '0')).map(e => e === '0' ? '10' : e).reduce((acc, cur) => Number(acc) + Number(cur), 0) / 10;
        if(X > 1) res = `${X}x`;
        if(X === 1) res = 'x';
    }
    if(numbers.length > 0) {
        numbers = numbers.reduce((acc, cur) => acc + cur, 0);
        res === '0' ? res = numbers.toString() : res += ' + ' + String(numbers);
    }
    return res;
}
```