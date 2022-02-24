---
layout: post
title:  "[Algorithm] 선택 정렬"
date:   2021-01-05
description: "C++ Selection Sort"
tag: 
- C++
- Sort
- algorithm
comments: true
---

## <center>[Algorithm] 선택 정렬</center>  

>[Git Source](https://github.com/chanos-dev/Algorithm-DataStructure/tree/master/DataStructure/0x01 Sort/SelectionSort)

---

> <b> Selection Sort </b> 🤏
 
- 가장 작은 것을 선택해서 제일 앞으로 보내는 알고리즘

```cpp
#include<iostream>
using namespace std;

int main(void)
{
	int i, j, min, index, temp;
	int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};

	for(i = 0; i < 10; i++)
	{
		min = 9999;
		for (j = i; j < 10; j++)
		{
			if(min > array[j])
			{
				min = array[j];
				index = j;
			}
		}
		temp = array[i];
		array[i] = array[index];
		array[index] = temp;
	}
	
	for(i = 0; i < 10; i++)
		cout<<array[i]<<" ";
	
	return 0;
}
``` 

> Selection Sort

 1. **<span style="color:green">1</span>, 10, 5, 8, 7, 6, 4, 3, 2, 9**

 2. **1, <span style="color:red">10</span>, 5, 8, 7, 6, 4, 3, <span style="color:blue">2</span>, 9**

 3. **1, 2, <span style="color:red">5</span>, 8, 7, 6, 4, <span style="color:blue">3</span>, 10, 9**

 4. **1, 2, 3, <span style="color:red">8</span>, 7, 6, <span style="color:blue">4</span>, 5, 10, 9**

 5. **1, 2, 3, 4, <span style="color:red">7</span>, 6, 8, <span style="color:blue">5</span>, 10, 9**

 6. **1, 2, 3, 4, 5, <span style="color:green">6</span>, 8, 7, 10, 9**

 7. **1, 2, 3, 4, 5, 6, <span style="color:red">8</span>, <span style="color:blue">7</span>, 10, 9**

 8. **1, 2, 3, 4, 5, 6, 7, <span style="color:green">8</span>, 10, 9**

 9. **1, 2, 3, 4, 5, 6, 7, 8, <span style="color:red">10</span>, <span style="color:blue">9</span>**

 0. **1, 2, 3, 4, 5, 6, 7, 8, 9, 10**


- 최소 값을 구하기 위해 배열안에 있는 값보다 큰 값을 임의로 세팅을 한다 (min = 9999)
- index 0 부터 시작해 가장 작은 수를 구한다.
- 가장 작은 수가 정해졌으면 해당 값의 index를 시작 위치의 index와 [swap]({{ site.url }}/swap/) 한다.
- 선택 정렬의 시간 복잡도는 `O(N^2)`