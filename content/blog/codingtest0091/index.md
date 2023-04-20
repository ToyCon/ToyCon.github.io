---
title: 캐릭터의 좌표
date: "2023-04-19T19:55:07.284Z"
description: "Coding Test"
---
### 캐릭터의 좌표    
https://school.programmers.co.kr/learn/courses/30/lessons/120861    
    
#### 변수    
배열 keyinput    
맵의 크기 board    
    
#### 제한사항    
캐릭터는 항상 [0,0]에서 시작    
board은 [가로 크기, 세로 크기] 형태    
board의 가로 크기와 세로 크기는 홀수    
board의 크기를 벗어난 방향키 입력은 무시    
0 ≤ keyinput의 길이 ≤ 50    
1 ≤ board[0] ≤ 99    
1 ≤ board[1] ≤ 99    
keyinput은 항상 up, down, left, right만 주어짐    
    
#### 풀이    
1. 상수 res 선언하고 [0, 0] 할당    
2. 상수 limit 선언하고 [Math.trunc(board[0] / 2), Math.trunc(board[1] / 2)] 할당    
3. for (e of keyinput) 반복문 진입    
4. 조건문으로 e 값 확인, e === 'up'일 때 res[1]++, Math.abs(res[1]) > limit[1] 이면 res[1]--    
5. e === 'down'일 때 res[1]--, Math.abs(res[1]) > limit[1] 이면 res[1]++    
6. e === 'left'일 때 res[0]--, Math.abs(res[0]) > limit[0] 이면 res[0]++    
7. e === 'right'일 때 res[0]++, Math.abs(res[0]) > limit[0] 이면 res[0]--    
8. res 반환    
    
#### 코드    
switch를 사용한 구문이 깔끔하게 정리가 되어 있고 길이도 크게 길지 않았다. switch를 활용하는 경우를 찾아봐야겠다.    
```JavaScript
function solution(keyinput, board) {
    const res = [0, 0];
    const limit = [Math.trunc(board[0] / 2), Math.trunc(board[1] / 2)];
    for (e of keyinput){
        if (e === 'up') {
            res[1]++;
            if(Math.abs(res[1]) > limit[1]) res[1]--;
        }
        if (e === 'down') {
            res[1]--;
            if(Math.abs(res[1]) > limit[1]) res[1]++;
        }
        if (e === 'left') {
            res[0]--;
            if (Math.abs(res[0]) > limit[0]) res[0]++;
        }
        if (e === 'right') {
            res[0]++;
            if (Math.abs(res[0]) > limit[0]) res[0]--;
        }
    }
    return res;
}
```