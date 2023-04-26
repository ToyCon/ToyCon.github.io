---
title: 옷가게 할인 받기
date: "2023-03-31T17:15:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120818"
---
### 옷가게 할인 받기    
https://school.programmers.co.kr/learn/courses/30/lessons/120818    
    
#### 변수    
구매한 옷의 가격 price    
    
#### 제한사항    
10 ≤ price ≤ 1,000,000    
price는 10원 단위(1의 자리가 0)    
소수점 이하를 버린 정수를 반환    
    
#### 풀이    
조건문을 통해서 price의 할인 조건을 확인 후 할인된 가격을 반환하는 방식으로 풀었다.    
1. price >= 500000 확인, 맞으면 price * 8 / 10에서 소수점 이하를 버린 값을 반환     
2. price >= 300000 확인, 맞으면 price * 9 / 10에서 소수점 이하를 버린 값을 반환     
3. price >= 100000 확인, 맞으면 price * 95 / 100에서 소수점 이하를 버린 값을 반환     
4. 조건을 모두 만족하지 않으면 price를 반환    
    
#### 코드    
```JavaScript
function solution(price) {
    return Math.trunc(price >= 500000 ? price * 8 / 10 : price >= 300000 ? price * 9 / 10 : price >= 100000 ? price * 95 / 100 : price);
}
```