---
title: TIL6
date: "2023-05-01T21:20:00.000Z"
description: "5월 1일 학습일지"
---
소인수분해를 구현하는 문제를 푸는데 많은 시간을 썼다. 아쉽다. 앞으로 미흡하다고 생각하는 부분은 미루지 않고 이해가 될때까지 풀어보려고 한다.    
1. 연습문제 풀기    
2. 소수를 판별하는 함수 작성 중 에러가 발생하여 해당 에러 메시지를 검색하고 해결 방법 정리(포스트 작성 중)    
3. 소인수분해 알고리즘 학습    
**내가 생각하지 못했던 부분은 while 반복문 사용, 중복되는 원소를 걸러주는 set 객체 사용    
**내가 생각하기에 직관적으로 이해가 제일 잘됐던 구현(https://dalconbox.tistory.com/288)    
```JavaScript
var fs = require('fs');
var input = fs.readFileSync('/dev/stdin').toString().split(' ');
var num = parseInt(input[0]);
 
var i = 2;
var primes = []
while (true) {
  if (num % i === 0) {
    num = num / i
    primes.push(i)
    i = 1;
  }
  i++;
  if (i > num) {
    break;
  }
}
 
console.log(primes.join("\n"));
```
4. 수의 범위를 정해야 하는 경우 제곱근을 쓰면 왜 시간복잡도가 줄어드는지 이해함 → '좌우대칭'을 기억하자    
5. 소인수분해 2부터 시작해서 순서대로 나누는 과정을 console.log로 보여주는 코드 → https://rheem-hm.tistory.com/48