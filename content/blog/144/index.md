---
title: 저주의 숫자 3
date: "2023-04-03T10:56:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120871"
---
### 저주의 숫자 3    
https://school.programmers.co.kr/learn/courses/30/lessons/120871    
    
#### 변수    
정수 배열 n    
    
#### 제한사항    
1 ≤ n ≤ 100    
    
#### 풀이    
숫자 3이 등장하면 안되고, 3의 배수도 사용할 수 없다. 이 조건들을 그대로 만족하는 식은 작성하기 어렵고 직관적이지 않다고 생각해서, 반복문을 써서 조건을 만족하는 경우에 변환되는 숫자에 1씩 더해서 조건을 피하는 방식으로 변환했다.    
1. 변수 res 선언하고 0 할당    
2. for(i = 0; i < n; i++) 반복문 진입    
3. res + 1    
4. res가 3의 배수인지 확인, 맞으면 res + 1    
5. res 끝자리 3 여부 확인, 맞으면 res + 1    
6. res 10의 자리 3 여부 확인, 맞으면 res + 10    
7. res 반환    
    
#### 코드    
실제 코드를 작성한 다음 오류를 체크하면서 계산해보니 처음에 순서대로 작성한 알고리즘과는 조금 달라졌다. 변환의 경우 53 → 54 → 55와 같이 두 번 연속으로 변환해야 하는 경우가 있어 같은 조건을 한 번 더 체크하는 방식으로 해결했다. 다른 풀이를 보니 대체로 정규표현식이나 배열을 생성하는 과정을 통해서 문제를 해결했다. for 반복문 i를 쓰면서 i에 3이 포함되지 않은 경우 별도로 선언된 카운트를 올리는 방식으로 i를 바로 반환하는 풀이가 제일 직관적이었던 것 같다. 정규표현식은 잊을만하면 항상 찾게 되는데 아직까지 자유자재로 쓰진 못하는 것 같다. 자주 찾아봐야겠다.    
```JavaScript
function solution(n) {
    let res = 0;
    for(i = 0; i < n; i++) {
        res+=1;
        if(Math.trunc(res % 100 / 10) === 3) res += 10;
        if(res % 3 === 0) res+=1;
        if(res % 10 === 3) res+=1;       
        if(res % 3 === 0) res+=1;
    }
    return res;
}
```