---
title: /Algorithms
layout: post
permalink: /Algorithms/BubbleSort
---

2020.7.31
<br/>
<br/>

# BubbleSort  
<br/>
  
옆에 있는 값과 비교해서 더 작은 값을 앞으로 보내기

반복적으로 두 숫자를 비교해서 더 작은 수를 앞으로 보낸다.
각 싸이클마다 가장 큰 값이 맨 뒤로 보내져
컴퓨터 내부 연산이 가장 비효율적으로 늘어나

시간 복잡도는 선택정렬과 동일하다
<br/>

```c
#include<stdio.h>

int main(void){
    int i, j, temp;
    int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};
    for(i = 0 ; i < 10 ; i++){
        for(j = 0 ; j < 9 - i; j++){
            if(array[j] > array[j+1]){
                temp = array[j];
                array[j] = array[j + 1];
                array[j+1] = temp;
            }
        }
    }
    for (i = 0; i < 10 ; i++){
        printf(" %d", array[i]);
    }    
}
```



