---
title: 숨어있는 숫자의 덧셈 (1)
date: "2023-03-30T15:10:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120851"
---
### 숨어있는 숫자의 덧셈 (1)    
https://school.programmers.co.kr/learn/courses/30/lessons/120851    
    
#### 변수    
문자열 my_string    
    
#### 제한사항    
1 ≤ my_string의 길이 ≤ 1,000    
my_string은 소문자, 대문자 그리고 한자리 자연수로 구성    
    
#### 풀이    
배열로 분해하여 숫자만 골라내는 과정을 적용했다.    
1. split('') 메서드 써서 배열로 분해    
2. 배열의 각 원소를 강제로 number 타입으로 변환했을 때 NaN 여부를 확인    
3. 숫자로 변환    
4. 모든 원소의 합을 반환    
    
#### 코드    
reduce 메서드의 콜백에서 자꾸 이상한 결과가 나와서 결국 map 메서드를 써서 number 타입으로 전체 형변환을 해버렸다. 다른 사람들의 풀이를 보니 reduce의 콜백에서 acc와 cur을 모두 강제로 paresInt 함수로 number 타입으로 강제로 바꿔서 연산을 했는데, 아마 이 부분을 내가 놓친 것 같다.    
```JavaScript
function solution(my_string) {
    return my_string.split('').filter(e => !isNaN(Number(e))).map(e => e = Number(e)).reduce((acc, cur) => acc + cur, 0);
}
```