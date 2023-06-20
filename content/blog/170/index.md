---
title: 문자열 정렬하기 (1)
date: "2023-04-28T21:26:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120850"
---
### 문자열 정렬하기 (1)    
https://school.programmers.co.kr/learn/courses/30/lessons/120850    
    
#### 변수    
문자열 my_string    
    
#### 제한    
1 ≤ my_string의 길이 ≤ 100    
my_string에는 숫자가 한 개 이상 포함되어 있음    
my_string은 영어 소문자 또는 0부터 9까지의 숫자로 이루어져 있음    
    
#### 풀이    
숫자를 오름차순으로 골라내서 배열로 반환해야 한다. 메서드를 써서 쉽게 반환할 수 있기 때문에 순서를 고민했다.    
1. my_string.replaceAll(/[a-z]/g,'') 실행    
2. split 메서드로 배열로 분해    
3. map 메서드로 e => Number(e) 변환    
4. sort 메서드로 오름차순 정렬 후 반환    
    
#### 코드    
풀이가 다양했다. 모르는 부분들을 잘 체크해야겠다.    
```JavaScript
function solution(my_string) {
    return my_string.replaceAll(/[a-z]/g,'').split('').map(e => Number(e)).sort((a, b) => a - b);
}
```