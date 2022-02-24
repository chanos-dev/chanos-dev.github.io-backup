---
layout: post
title:  "[Algorithm] 삽입 정렬"
date:   2021-01-10
description: "C++ Insertion Sort"
tag: 
- C++
- Sort
- algorithm
comments: true
---

## <center>[Algorithm] 삽입 정렬</center>  

>[Git Source](https://github.com/chanos-dev/Algorithm-DataStructure/tree/master/DataStructure/0x01 Sort/InsertionSort)

---

> <b> Insertion Sort </b> 👇
 
- 각 숫자를 적절한 위치에 삽입을 하는 알고리즘
- 삽입 정렬 같은 경우는 `필요할 때`만 위치를 바꾸게 됩니다.

```cpp
#include<iostream>
using namespace std;

int main(void)
{
	int i, j;
	int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};
  
	for(i = 0; i < 9; i++)
	{
		j = i;
        
		while(array[j] > array[j+1])
		{
			temp = array[j];
			array[j] = array[j+1];
			array[j+1] = temp;
			j--;
			if(j < 0) break;
		}
  	}
   
	for(i = 0; i < 10; i++)
	{
		cout<<array[i]<<" ";
	}
	
	return 0;
}
``` 

> Insertion Sort

 1. **1, <span style="color:red">10</span>, <span style="color:red">5</span>, 8, 7, 6, 4, 3, 2, 9**
 
 2. **1, 5, <span style="color:red">10</span>, <span style="color:red">8</span>, 7, 6, 4, 3, 2, 9**

 3. **1, 5, <span style="color:red">8</span>, <span style="color:red">10</span>, <span style="color:red">7</span>, 6, 4, 3, 2, 9**

 4. **1, 5, <span style="color:red">7</span>, <span style="color:red">8</span>, <span style="color:red">10</span>, <span style="color:red">6</span>, 4, 3, 2, 9**

 5. **1, <span style="color:red">5</span>, <span style="color:red">6</span>, <span style="color:red">7</span>, <span style="color:red">8</span>, <span style="color:red">10</span>, <span style="color:red">4</span>, 3, 2, 9**

 6. **1, <span style="color:red">4</span>, <span style="color:red">5</span>, <span style="color:red">6</span>, <span style="color:red">7</span>, <span style="color:red">8</span>, <span style="color:red">10</span>, <span style="color:red">3</span>, 2, 9**

 7. **1, <span style="color:red">3</span>, <span style="color:red">4</span>, <span style="color:red">5</span>, <span style="color:red">6</span>, <span style="color:red">7</span>, <span style="color:red">8</span>, <span style="color:red">10</span>, <span style="color:red">2</span>, 9**

 8. **1, 2, 3, 4, 5, 6, 7, 8, <span style="color:red">10</span>, <span style="color:red">9</span>**

 9. **1, 2, 3, 4, 5, 6, 7, 8, 9, 10**

- 삽입 정렬은 왼쪽이 이미 정렬이 되어있다는 가정하에 연산이 된다.
- 만약 데이터가 거의 정렬된 상태라면 제일 효율적으로 연산이 이루어진다.
- 삽입 정렬의 시간 복잡도는 `O(N^2)`이다.