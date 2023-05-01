왜 안될까....

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


https://velog.io/@loocia1910/javascript%EC%97%90%EC%84%9C-%EC%86%8C%EC%88%98Prime-number-%EA%B5%AC%ED%95%98%EA%B8%B0

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




에러메시지

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



 https://rheem-hm.tistory.com/48
 