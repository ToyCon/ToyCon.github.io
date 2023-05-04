---
title: 최댓값 만들기 (2)
date: "2023-05-04T14:16:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120862"
---
### 최댓값 만들기 (2)    
https://sc5o04.13o45ammers.co.kr/learn/courses/30/lessons/120862    
    
#### 변수    
정수 배열 numbers    
    
#### 제한    
-10,000 ≤ numbers의 원소 ≤ 10,000    
2 ≤ numbers 의 길이 ≤ 100    
    
#### 풀이    
처음에는 조건이 매우 까다롭다고 생각했다. 두 번째로 큰 수가 0이거나, 혹은 숫자가 하나만 양수고 나머지 숫자가 모두 음수이거나 하는 경우를 생각해봤다. 그런데 더 고민해보니 음수와 음수를 곱할 경우 양수가 되니 그냥 음수와 양수를 곱하는 경우만 피하면 된다는 결론이 나왔다. numbers에 100개의 원소가 다 들어있고 양수가 50개, 음수가 50개 들어있는 경우를 가정하여, 오름차순으로 정렬한뒤 numbers의 맨 앞의 원소 두개의 곱과 맨 뒤의 원소 두개의 곱을 비교하는 방법을 생각했다. numbers의 원소가 최소 2개이기 때문에, 모든 경우에 이 방법을 적용할 수 있다고 생각하여 이 방법 그대로 답을 반환했다.    
1. 상수 arr 선언하고 [...numbers].sort((a, b) => b - a) 할당    
2. 변수 length 선언하고 Number(arr.length) - 1 할당    
3. 삼항연산자로 arr[0] * arr[1] >= arr[length] * arr[length - 1] 확인    
4. 맞으면 arr[0] * [1] 반환, 틀리면 arr[length] * arr[length - 1] 반환    
    
#### 코드    
다른 풀이를 보니 방식은 똑같고 삼항연산자 대신 Math.max 메서드로 두 값을 비교했는데 이 쪽이 더 깔끔해보인다. 아직 메서드 사용이 서투른 것 같다. 더 공부해야겠다.    
```JavaScript
function solution(numbers) {
    const arr = [...numbers].sort((a, b) => b - a);
    let length = Number(arr.length) - 1;
    return arr[0] * arr[1] >= arr[length] * arr[length - 1] ? arr[0] * arr[1] : arr[length] * arr[length - 1];
}
```