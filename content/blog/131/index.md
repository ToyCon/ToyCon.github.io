---
title: 컨트롤 제트
date: 2023-03-23 21:47:00 +0900
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120853"
---
### 컨트롤 제트   
https://school.programmers.co.kr/learn/courses/30/lessons/120853    
    
#### 변수    
문자열 s    
    
#### 제한사항    
1 ≤ s의 길이 ≤ 200    
-1,000 < s의 원소 중 숫자 < 1,000    
s는 숫자, "Z", 공백    
s에 있는 숫자와 "Z"는 서로 공백으로 구분    
연속된 공백은 주어지지 않음    
0을 제외하고는 0으로 시작하는 숫자는 없음    
s는 "Z"로 시작하지 않음    
s의 시작과 끝에는 공백이 없음    
"Z"가 연속해서 나오는 경우는 없음    
    
#### 순서    
공백으로 구분된 문자열 형태로 주어지므로 배열로 나눈 뒤 반복문을 적용하는 방식으로 풀었다.    
1. 변수 res 선언하고 0 할당    
2. s를 공백 문자열로 split해서 배열로 재할당    
3. 배열 s에서 "Z"가 아닌 모든 원소를 숫자로 변환    
4. for (i = 0; i < s.length; i++) 반복문 진입    
4. s[i] === 'Z' 일 때 res -= s[i - 1]    
5. 그 외의 경우 res += s[i]    
6. res 반환    
    
#### 코드    
코드를 작성하면서 reduce 메서드를 떠올렸는데 Z의 경우를 처리하는 게 불편하다고 생각해서 반복문으로 풀었다. 다른 사람들의 풀이를 보니 reduce를 사용한 풀이가 보이는데 보면서 어떻게 사용했는지 분석을 해봐야겠다.    
```JavaScript
function solution(s) {
    let res = 0;
    s = s.split(" ").map(e => e === "Z" ? e : Number(e));
    for (i = 0; i <s.length; i++) s[i] === "Z" ? res-=s[i - 1] : res+=s[i];
    return res;
}
```
