---
title: 모스부호 (1)
date: "2023-03-27T09:59:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120838"
---
### 모스부호 (1)    
https://school.programmers.co.kr/learn/courses/30/lessons/120838    
    
#### 변수    
문자열 letter    
    
#### 제한사항    
1 ≤ letter의 길이 ≤ 1,000    
return값은 소문자    
letter의 모스부호는 공백으로 나누어져 있음    
letter에 공백은 연속으로 두 개 이상 존재하지 않음    
해독할 수 없는 편지 없음    
편지의 시작과 끝에는 공백이 없음    
    
#### 풀이    
공백으로 나누어져 있으므로 배열로 쉽게 분해할 수 있다. 신호를 키, 문자를 값으로 하는 객체를 선언한 다음 letter를 분해한 배열의 모든 원소를 변환한 다음 합쳐서 반환하는 방식으로 접근했다.    
1. 상수 morse 선언하고 모스 부호 객체 할당    
2. letter.split(' ') 적용해서 배열로 분해    
3. 메서드로 letter의 모든 요소에 대해서 e => e = mores[`${e}`] 콜백을 실행하는 메서드 적용    
4. letter.join('') 반환    
        
#### 코드    
join 메서드와 split 메서드를 합쳐서 reduce 메서드로 한 번에 푸는 방법이 매우 적절해 보인다. 잊지 말고 앞으로 적용해야겠다.    
```JavaScript
function solution(letter) {
    const morse = { 
        '.-':'a','-...':'b','-.-.':'c','-..':'d','.':'e','..-.':'f',
        '--.':'g','....':'h','..':'i','.---':'j','-.-':'k','.-..':'l',
        '--':'m','-.':'n','---':'o','.--.':'p','--.-':'q','.-.':'r',
        '...':'s','-':'t','..-':'u','...-':'v','.--':'w','-..-':'x',
        '-.--':'y','--..':'z'
    }
    letter = letter.split(' ').map(e => e = morse[`${e}`])
    return letter.join('');
}
```