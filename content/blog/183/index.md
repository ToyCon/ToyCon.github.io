---
title: 외계어 사전
date: "2023-05-12T22:40:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120869"
---
### 외계어 사전    
https://school.programmers.co.kr/learn/courses/30/lessons/120869    
    
#### 변수    
배열 spell    
사전 dic    
    
#### 제한    
spell과 dic의 원소는 알파벳 소문자로만 이루어져 있음    
2 ≤ spell의 크기 ≤ 10    
spell의 원소의 길이는 1    
1 ≤ dic의 크기 ≤ 10    
1 ≤ dic의 원소의 길이 ≤ 10    
spell의 원소를 모두 사용    
spell의 원소를 모두 사용해 만들 수 있는 단어는 dic에 두 개 이상 존재하지 않음    
dic과 spell 모두 중복된 원소를 갖지 않음    
    
#### 풀이    
알파벳 문자는 배열에 담은 상태에서 sort 메서드로 정렬이 가능하기 때문에, 알파벳을 오름차순으로 정렬한 값을 비교하여 일치하는 값이 있는지 확인하는 방식으로 풀었다.    
1. 변수 res 선언하고 2 할당    
2. 변수 word 선언하고 spell을 오름차순으로 정렬한 뒤 string 타입으로 묶어서 할당    
3. 변수 dictionary 선언하고 2와 같은 과정으로 원소를 오름차순으로 정렬한 배열을 할당    
4. 배열의 모든 원소 중 word와 같은 값이 있는지 확인하여 있으면 res에 1 할당    
5. res 반환    
    
#### 코드    
some 메서드를 사용해서 아주 쉽게 푼 문제가 있었다. 꼭 기억해야겠다.    
```JavaScript
function solution(spell, dic) {
    let res = 2;//기본값으로 일치하는 항목이 없다고 가정하고 2 할당
    let word = [...spell].sort().join('');//알파벳 순으로 정렬
    let dictionary = [...dic].map(e => [...e].sort().join(''));//dic의 원소를 알파벳 순으로 정렬, word와 같은 방식
    if(dictionary.find(e => e === word)) res = 1;//dictonary의 원소 중 word와 같은 원소가 있으면 res를 1로 변환
    return res;
}
```