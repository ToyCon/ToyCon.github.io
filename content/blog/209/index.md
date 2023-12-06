---
title: C언어 학습 1
date: "2023-11-27T23:26:00.000Z"
description: "IDE, stdio.h"
---
1. Visual Studio    
    - 통합 개발 환경(IDE): 프로그램 개발에 사용되는 코드 작성, 디버깅, 컴파일, 배포 등 모든 과정을 통합적으로 관리할 수 있도록 해주는 소프트웨어. VS 외에도 eclise같은 소프트웨어도 있음    
    - 클라우드 기반의 IDE 서비스도 있음: [ideone](https://ideone.com/), [goorm](https://ide.goorm.io/)    
    - vscode는 '코드 에디터'. 가벼우며, 필요한 기능은 확장 프로그램을 설치해서 추가할 수 있음    
    - [Visual Studio와 VS CODE를 비교한 기사](https://www.itworld.co.kr/news/130999)    
2. stdio.h    
    - 헤더파일의 일종. stdio는 STanDard Input Output의 약자.    
    - C언어의 표준 입출력 헤더 파일, 콘솔 입/출력을 할때, 외부 파일을 읽을 때 사용. Hello world 출력, CLI에서 조작 등 자주 보게 되는 헤더 파일임    
    - 헤더 파일은 time.h, math.h 등 다양한 종류가 있으며 필요하면 소스 파일 맨 윗줄에 불러와서 사용하면 된다.    
    ```c
    #include <stdio.h>
    
    int main(void) {
      printf("Hello World!");
      return 0;
    }
    ```
3. 소스 코드가 실행 파일로 변하는 과정    
    - 설계도 -(에디터)→ 소스코드 -(전처리기)→ 향상된 소스코드 -(컴파일러)→ 목적코드 -(링커)→ 실행파일