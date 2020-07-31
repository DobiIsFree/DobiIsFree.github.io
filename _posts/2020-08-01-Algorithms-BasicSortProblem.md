---
title: /Algorithms
layout: post
permalink: /Algorithms/BasicSortingProblem
---

2020.08.01
<br/>

## Basic Sorting Problem
<br/>

(1) 2750 : 수 정렬하기

> ### 문제
N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.

<br/>

> ### 입력
첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000)이 주어진다. 둘째 줄부터 N개의 줄에는 숫자가 주어진다. 이 수는 절댓값이 1,000보다 작거나 같은 정수이다. 수는 중복되지 않는다.

<br/>

> ### 출력
첫째 줄부터 N개의 줄에 오름차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.

<br/>

>> 
```c
#include <stdio.h>

int array[1001];

int main(void){
    int number, i, j, min, index, temp;
    scanf("%d", &number);
    for(i = 0 ; i < number ; i++){
        scanf("%d", &array[i]);
    }
    for(i = 0 ; i < number ; i++){
        min = 1001;
        for(j = i ; j < number ; j++){
            if (min > array[j]){
                min = array[j];
                index = j;
            }
        }
        temp = array[i];
        array[i] = array[index];
        array[index] = temp;
    }
    for(i = 0 ; i < number ; i++) {
        printf("%d\n", array[i]);
    }
}
```

<br/>
(2) 2752 : 세수정렬

> ### 문제
동규는 세수를 하다가 정렬이 하고싶어졌다.
숫자 세 개를 생각한 뒤에, 이를 오름차순으로 정렬하고 싶어 졌다.
숫자 세 개가 주어졌을 때, 가장 작은 수, 그 다음 수, 가장 큰 수를 출력하는 프로그램을 작성하시오.

<br/>

> ### 입력
숫자 세 개가 주어진다. 이 숫자는 1보다 크거나 같고, 1,000,000보다 작거나 같다. 이 숫자는 모두 다르다.

<br/>

> ### 출력
제일 작은 수, 그 다음 수, 제일 큰 수를 차례대로 출력한다.

<br/>

>> 
```c
#include <stdio.h>

int array[3];

int main(void){
    int i, j, min, index, temp;

    for(i = 0 ; i < 3 ; i++){
        scanf("%d", &array[i]);
    }
    for(i = 0 ; i < 3 ; i++){
        min = 1000001;
        for(j = i ; j < 3 ; j++){
            if (min > array[j]) {
                min = array[j];
                index = j;
            }
        }
        temp = array[i];
        array[i] = array[index];
        array[index] = temp;
    }
    for(i = 0 ; i < 3 ; i++) {
        printf("%d ", array[i]);
    }
}
```