---
title: /Algorithms
layout: post
permalink: /Algorithms/MergeSort 
---

2020.08.01
<br/>

## Merge Sort 
<br/>

퀵 정렬과 마찬가지로 분할 정복을 사용하지만 정확히 반으로 나누고 나중에 정렬한다는 점에서 O(N * log N)의 시간 복잡도를 보장한다.

<br/>

> 
```c
#include <stdio.h>

int number = 8;
int sorted[8]; // 메모리의 불필요한 사용을 막기 위해 : 정렬 배열은 반드시 전역 변수로

void merge(int a[], int m, int mid, int n) {
    int i = m;
    int j= mid + 1;
    int k = m;

    // 작은 순서대로 배열에 삽입
    while (i <= mid && j <= n) {
        if (a[i] <= a[j]){
            sorted[k] = a[i];
            i++;
        } else {
            sorted[k] = a[j];
            j++;
        }
        k++;
    }

    // 남은 데이터 삽입
    if(i > mid){
        for(int t = j ; t <= n ; t++) {
            sorted[k] = a[t];
            k++;
        }
    } else {
        for (int t = i ; t <= mid ; t++){
            sorted[k] = a[t];
            k++;
        }
    }

    // 정렬된 배열을 원래 배열에 삽입
    for(int t = m ; t <= n ; t++){
        a[t] = sorted[t];
    }
}

void mergeSort(int a[], int m, int n){
    if (m < n){
        int mid = (m + n) / 2;
        mergeSort(a, m, mid);
        mergeSort(a, mid + 1, n);
        merge(a, m, mid, n);
    }
}

int main(void) {
    int array[] = {7, 6, 5, 8, 3, 5, 9, 1};
    mergeSort(array, 0, number - 1);
    for(int i = 0 ; i < number ; i++){
        printf("%d ", array[i]);
    }
}
```
