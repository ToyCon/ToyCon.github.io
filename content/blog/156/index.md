---
title: 진료 순서 정하기
date: "2023-04-18T11:38:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120835"
---
### 진료 순서 정하기    
https://school.programmers.co.kr/learn/courses/30/lessons/120835    
    
#### 변수    
정수 배열 emergency    
    
#### 제한사항    
중복된 원소 없음    
1 ≤ emergency의 길이 ≤ 10    
1 ≤ emergency의 원소 ≤ 100    
    
#### 풀이    
emergency 배열을 내림차순으로 정렬한 새로운 배열을 받은 다음, 반복문을 통해 메서드로 인덱스 넘버를 받는 방식으로 풀었다.    
1. 상수 dig 선언하고 emergency를 복사한 배열을 내림차순으로 정렬    
2. 상수 res 선언하고 빈 배열 할당    
3. for(i=0, i < emergency.length, i++) 반복문 실행    
4. 반복문 내부에서 res.push(dig.findIndex(e => e === emergency[i]) + 1) 실행    
5. res 반환    
    
#### 코드    
for 반복문을 forEach 메서드로 대체해서 풀었다. 다른 풀이를 보니 별도의 배열을 선언해서 정렬한 것은 같은데 emergency에 바로 map을 적용해서 푸는 방식이 많았다. indexOf 메서드를 썼는데 더 간단한 방법인 것 같다. 기억해야겠다.    
```JavaScript
function solution(emergency) {
    const dig = [...emergency].sort((a, b) => b - a);
    const res = [];
    emergency.forEach(ele => res.push(dig.findIndex(e => e === ele) + 1));
    return res;
}
```