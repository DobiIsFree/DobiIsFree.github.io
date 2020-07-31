---
title: /Algorithms
layout: post
permalink: /Algorithms/QuickSort
---

2020.08.01
<br/>

## Quick Sort  
<br/>
'분할 정복'알고리즘 -> 평균 속도 O(N * log N)
선택/버블/삽입 정렬과 비교하면 굉장히 빠른 속도

'특정한 값'을 기준으로 큰 숫자와 작은 숫자로 나눈다 (두 집합으로 분리)  
이때 '특정한 값' = pivot, 보통 처음 값으로 설정한다

<br/>
[ '3' 7 2 8 1 5 9 6 10 2 4]     (pivot = 3)
<br/>
[ '3' __7__ 2 8 1 5 9 6 10 __2__ 4]
<br/>
'3'을 기준으로 왼쪽에서 '3'보다 큰 값, 오른쪽에서 '3'보다 작은 값을 선택해서 바꿔준다.
<br/>
위의 동작을 반복적으로 수행하다가 피봇보다 큰 값의 인덱스가 작은 값의 인덱스가 커지는 순간 피봇과 작은 값을 교환한다.
<br/>
[ 1 2 3 '8' 5 9 6 10 7 4]       (pivot = 8)
<br/>
3을 기준으로 왼쪽과 오른쪽에 작은값과 큰 값으로 분리된 것을 볼 수 있다.

<br/>
이미 정렬된 경우 분할 정복의 이점을 사용할 수 없다.
또한 편향되게 분할될 가능성이 있어 최악의 경우 O(N^2)의 시간 복잡도를 가질 수 있다.

<br/>
```c
#include<stdio.h>

int number = 10;
int data[] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};

void show() {
    int i;
    for(i = 0 ; i < 10 ; i++){
        printf("%d ", data[i]);
    }
}

void quickSort(int* data, int left, int right) {
    if (left >= right)
        return;
    
    int pivot = left;
    int i = left + 1; 
    int j = right;
    int temp;

    while (i <= j) {
        while (i <= right && data[i] <= data[pivot]) {
            i++;
        }
        while (j > left && data[j] >= data[pivot]) {
            j--;
        }
        if (i > j) {
            temp = data[j];
            data[j] = data[pivot];
            data[pivot] = temp;
        } else {
            temp = data[j];
            data[j] = data[i];
            data[i] = temp;
        }
    }

    quickSort(data, left, j - 1);
    quickSort(data, j + 1, right);
    
}

int main(void){
    quickSort(data, 0, number - 1);
    show();
    return 0;
}
```


