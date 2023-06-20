---
title: 소인수분해 문제를 풀면서 발생했던 오류 파헤치기
date: "2023-05-01T17:25:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120852"
---
내가 처음에 소인수분해 문제를 풀면서 작성했던 코드는 이거였다(틀린 답이다).    
```JavaScript
function solution(n) {
    let res = [];
    if(n % 2 === 0) res.push(2);
    for(i = 3; i <= Math.trunc(Math.sqrt(n)); i += 2) 
        if(n % i === 0 && isPrime(i)) res.push(i);
    return res.length > 0 ? res : [n];
}

function isPrime(num) {
    if(num <= 1) return false;
    if(num % 2 === 0) return num === 2 ? true : false;
    for(i = 3; i <=Math.sqrt(num); i+=2) if(num % i === 0) return false;
    return true;
}
```
제대로 작성한것 같은데, 계속 아래와 같은 오류가 발생했다.    
    
```JavaScript
#
# Fatal error in , line 0
# Fatal JavaScript invalid size error 169220804
#
#
#
#FailureMessage Object: 0x7fff4a7255d0
 1: 0xb6ca81  [node]
 2: 0x1bef1a4 V8_Fatal(char const*, ...) [node]
 3: 0xe63268  [node]
 4: 0x1010b12  [node]
 5: 0x1011456  [node]
 6: 0x11d1b73 v8::internal::Runtime_GrowArrayElements(int, unsigned long*, v8::internal::Isolate*) [node]
 7: 0x15d5439  [node]
```
    
처음에는 소수 여부를 판별하는 isPrime 함수가 잘못되었나 싶어서 아래 함수를 복사해서 붙여넣었더니 정상적으로 작동했다(https://velog.io/@loocia1910/javascript%EC%97%90%EC%84%9C-%EC%86%8C%EC%88%98Prime-number-%EA%B5%AC%ED%95%98%EA%B8%B0).    

```JavaScript    
function isPrime(num) {
  if(num <= 1) { // 음수와 1은 소수가 아니다
    return false;
  }

  // 2는 짝수 중 유일한 소수이다
  if( num % 2 === 0) { 
    return num === 2 ? true : false;
  }
  
  // 이제 num이 홀수 일때 다른 수에 나눠지는지 판별한다
  
  // Math.sqrt(num) 즉, √num까지 나눠 떨어지는지 검사한다
  // 원리는 아래글 "에라토스테네스의 체" 참고
 
  const sqrt = parseInt(Math.sqrt(num));

  for( let divider = 3; divider <= sqrt; divider += 2) {

    if(num % divider === 0) {
      return false;
    }
    
  }
  
  return true;
}
```
내가 작성한 isPrime과 별 차이가 없다고 생각해서, 에러 메시지 자체를 검색하니 스택오버플로우 질문과 해당 질문의 답변을 한글로 번역한 포스트를 찾을수 있었는데, 심플한 오류 메시지 그대로 '메모리를 과하게 사용했다'가 결론이었다. 여기서 '메모리를 과하게 사용할 이유가 있나?' 싶어서 설마하는 마음에, 원래의 코드에서 isPrime함수의 for 반복문 변수명을 i에서 j로 바꿨다. 그랬더니 잘 작동한다.    
```JavaScript
function solution(n) {
    let res = [];
    if(n % 2 === 0) res.push(2);
    for(i = 3; i <= Math.trunc(Math.sqrt(n)); i += 2) 
        if(n % i === 0 && isPrime(i)) res.push(i);
    return res.length > 0 ? res : [n];
}

function isPrime(num) {
    if(num <= 1) return false;
    if(num % 2 === 0) return num === 2 ? true : false;
    let sqrt = Math.sqrt(num)
    for(j = 3; j <= Math.sqrt(num); j+=2) if(num % j === 0) return false;
    return true;
}
```
내 기억으론 분명히 변수의 범위는 함수 내부로 제한된다고 기억하고 있어서 같은 변수를 써도 된다고 생각했는데, 문제를 푸는 페이지 내부에서는 하나의 범위로 묶인 모양이다. 그래서 반복문마다 i가 계속 사용되는 바람에 메모리를 모두 점유하는 문제가 발생했다. 이 문제에 발을 좀 오래 묶여있어서, 앞으로 함수를 선언할 때 변수명도 겹치지 않게 잘 선택해야겠다는 교훈으로 마무리 지으려고 한다. 대신 변수 범위는 주말에 공부를 조금 해봐야겠다.