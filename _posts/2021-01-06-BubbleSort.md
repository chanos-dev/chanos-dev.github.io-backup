---
layout: post
title:  "[Algorithm] 버블 정렬"
date:   2021-01-05
excerpt: "C++ Bubble Sort"
tag: 
- C++
- Sort
- algorithm
comments: true
---

## <center>[Algorithm] 버블 정렬</center>  

>[Git Source](https://github.com/chanos-dev/Algorithm-DataStructure/tree/master/DataStructure/0x01 Sort/BubbleSort)

---

> <b> Bubble Sort </b> 🧼
 
- 옆에 있는 값과 비교해서 더 작은 값을 반복적으로 앞으로 보내는 알고리즘

```cpp
#include<iostream>
using namespace std;

int main(void)
{
	int i, j, temp;
	int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};

	for(i = 0; i < 10; i++)
	{
		for(j = 0; j < 9-i; j++)
		{
			if(array[j] > array[j+1])
			{
				temp = array[j];
				array[j] = array[j+1];
				array[j+1] = temp;
			}
		}
	}
	
	for(i = 0; i < 10; i++)
		cout<<array[i]<<" ";
	
	return 0;
}
``` 

> Bubble Sort

 1. **<span style="color:red">1</span>, <span style="color:red">10</span>, 5, 8, 7, 6, 4, 3, 2, 9**

 2. **1, <span style="color:red">10</span>, <span style="color:red">5</span>, 8, 7, 6, 4, 3, 2, 9**

 3. **1, 5, <span style="color:red">10</span>, <span style="color:red">8</span>, 7, 6, 4, 3, 2, 9**

 4. **1, 5, 8, <span style="color:red">10</span>, <span style="color:red">7</span>, 6, 4, 3, 2, 9**

 5. **1, 5, 8, 7, <span style="color:red">10</span>, <span style="color:red">6</span>, 4, 3, 2, 9**

 6. **1, 5, 8, 7, 6, <span style="color:red">10</span>, <span style="color:red">4</span>, 3, 2, 9**

 7. **1, 5, 8, 7, 6, 4, <span style="color:red">10</span>, <span style="color:red">3</span>, 2, 9**

 8. **1, 5, 8, 7, 6, 4, 3, <span style="color:red">10</span>, <span style="color:red">2</span>, 9**

 9. **1, 5, 8, 7, 6, 4, 3, 2, <span style="color:red">10</span>, <span style="color:red">9</span>**

 10. **1, 5, 8, 7, 6, 4, 3, 2, 9, 10**

 11. **1, 5, <span style="color:red">8</span>, <span style="color:red">7</span>, 6, 4, 3, 2, 9, 10**

 12. **1, 5, 7, <span style="color:red">8</span>, <span style="color:red">6</span>, 4, 3, 2, 9, 10**

 13. **...**

 14. **1, 2, 3, 4, 5, 6, 7, 8, 9, 10**

- 현재 인덱스에서 뒤에있는 인덱스와 비교하여 더 작은 값을 앞으로 보낸다.
- 버블 정렬같은 경우는 뒤에서부터 정렬이 완성이 된다.
- 버블 정렬의 시간복잡도는 선택정렬과 같은 `O(N^2)`이다.
- 선택정렬과 같은 시간복잡도지만 버블정렬은 매번 연산이 이루어지므로 정렬 중에서도 가장 느린 알고리즘에 속한다.