---
title: 공 던지기
date: "2023-04-21T17:15:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120843"
---
### 공 던지기    
https://school.programmers.co.kr/learn/courses/30/lessons/120843    
    
#### 변수    
정수 배열 numbers    
정수 K    
    
#### 제한사항    
공은 1번부터 던지며 오른쪽으로 한 명을 건너뛰고 그다음 사람에게만 던질 수 있음    
2 < numbers의 길이 < 100    
0 < k < 1,000    
numbers의 첫 번째와 마지막 번호는 실제로 바로 옆에 있음    
numbers는 1부터 시작하며 번호는 순서대로 올라감    
    
#### 풀이    
수열이라고 생각하고 10번째 값까지 적어보니 2n-1번째 값을 찾는 수열 문제임을 확인했다. 추가로 배열의 인덱스는 0부터 시작하기 때문에, 구하는 값은 2n - 2에 해당하는 numbers의 원소다. numbers의 길이보다 길 경우 길이로 나눈 나머지를 인덱스에 넣는 방식으로 값을 찾았다.    
1. 삼항연산자 조건으로 k * 2 - 2 > numbsers.length 확인    
2. 만족하면 numbers[(k * 2 - 2) % numbers.length]    
3. 그 외의 경우 numbers[k * 2 - 2]    
4. 3을 반환    
    
#### 코드    
다른 풀이를 살펴보니 2n - 2의 값을 numbers의 길이와 굳이 비교할 필요가 없었다. -- 연산자를 사용한 풀이도 있었는데 변수 앞에 먼저 --를 실행해서 k가 1일 때 바로 0으로 만드는 풀이도 있었다. 수열로 접근해서 너무 복잡하게 생각한 것 같다. 조건을 더 꼼꼼히 살펴서 더 계산을 줄일 수 있는지 항상 짚어봐야겠다.    
```JavaScript
function solution(numbers, k) {
    return k * 2 - 2 > numbers.length ? numbers[(k * 2 - 2) % numbers.length] : numbers[k * 2 - 2];
}
```