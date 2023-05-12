---
title: 안전지대
date: "2023-05-08T14:22:52.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120866"
---
### 안전지대    
https://school.programmers.co.kr/learn/courses/30/lessons/120866    
    
#### 변수    
2차원 배열 지도 board    
    
#### 제한    
board는 n * n 배열    
1 ≤ n ≤ 100    
지뢰는 1로 표시    
board에는 지뢰가 있는 지역 1과 지뢰가 없는 지역 0만 존재    
    
#### 풀이    
시간복잡도를 줄이는 방법을 고민했지만 별다른 수를 찾지 못했다. 나중에 다른 풀이를 보면서 공부해보기로 하고 반복문을 사용해서 모든 항목을 검사하되, 지뢰가 있는 칸이 나오면 반복문의 반복연산자에 숫자를 더해서 위험지역이 확실한 지역을 건너뛰는 방식을 적용했다.    
1. 변수 res 선언하고 0 할당    
2. 변수 n 선언하고 board.length를 number로 받아서 반환    
3. for (i = 0; i < n; i++) 반복문 진입 - 아래로 내려가는 반복문    
4. 2번 반복문 내부에서 for (j = 0; j < n; j++) 반복문 진입 - 우측으로 진행하는 반복문    
5. 변수 danger 선언하고 false 할당 - 검사해서 true로 바뀌면 res에 추가하지 않음    
6. for (k = i - 1; k <= i + 1; k++) 반복문 진입 - 윗줄 부터 아랫줄까지 검사    
7. k가 -1 또는 n 일때 continue - 검사 안함    
8. 5번 반복문 내부에서 for (l = j - 1; l <= j + 1; l++) 반복문 진입 - 왼쪽부터 오른쪽까지 검사    
9. l가 -1 또는 n 일때 continue - 검사 안함    
10. board[k][l] === 1 확인, 맞으면 danger에 true 할당    
11. 3번 반복문 내부에서 danger가 true인지 확인, 맞으면 j+=2, 틀리면 res++    
12. 모든 반복문 나와서 res 반환    

#### 코드    
테스트케이스가 공개되지 않아서 어떤 이유인지는 모르겠으나 11번 조건이 있을 때 조건을 통과하지 못하는 경우가 있었다. 2씩 더했을때와 1씩 더했을 때 통과하지 못하는 케이스가 다른 걸 봐서는 이런 형태의 조건은 정상적으로 작동하지 않는 모양이다. 짝수와 홀수의 경우로 나뉘는 듯 한데 이건 직접 연구를 해봐야겠다. 다른 사람들의 풀이를 보니 좌표를 미리 배열로 받은 다음 forEach 메서드를 두 번 사용해 반복문과 같은 방식으로 답을 낸 풀이가 있었다. 이 풀이를 해석해봐야겠다.    
```JavaScript
function solution(board) {
    let res = 0;
    let n = Number(board.length);
    for(i = 0; i < n; i++) {//board 전체에서 아래로 내려가는 반복문
        for(j = 0; j < n; j++) {//i번째 줄에서 우측으로 진행하는 반복문
            let danger = false;//위험 여부 확인
            for(k = i - 1; k <= i + 1; k++) {//윗줄부터 아래줄까지 검사
                if(k === -1 || k === n) continue;//배열의 범위 바깥을 검사하지 않음
                for(l = j - 1; l <= j + 1; l++) {//왼쪽부터 오른쪽까지 검사
                    if(l === -1 || l === n) continue;//배열의 범위 바깥을 검사하지 않음
                    if(board[k][l] === 1) danger = true;//지뢰가 있으면 위험
                }
            }
            if(!danger) res++;//풀이 11번 danger ? j+=2 : res++; 코드를 대체함
        }
    }
    return res;
}
```