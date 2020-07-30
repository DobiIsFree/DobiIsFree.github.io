---
title: /Algorithms
layout: post
permalink: /Algorithms/InsertionSort
---

## InsertionSort

각 숫자를 적절한 위치에 삽입
범위를 확장하면서 정렬 진행 
--> 최악의 경우 시간복잡도 O(N^2)
--> 최선의 경우 : 이미 정렬이 어느정도 되어있는 상태

'''
#include<stdio.h>

int main(void){
    int i, j, temp;
    int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};
    for(i = 0 ; i < 9 ; i++){
        j = i;
        while (array[j] > array[j+1]) {
            
            temp = array[j];
            array[j] = array[j + 1];
            array[j+1] = temp;
            j--;
            
        }
    }
    for (i = 0; i < 10 ; i++){
        printf(" %d", array[i]);
    } 
}
'''