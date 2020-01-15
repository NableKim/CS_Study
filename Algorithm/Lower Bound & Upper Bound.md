# 이분 탐색

- 원하는 k를 찾는 과정


## Lower Bound

- 원하는 값 k이상이 처음 나오는 위치를 찾는 과정
- ex) 정렬된 데이터 {1, 3, 5, 7, 9, 11} 에서 8이상인 값이 처음 나오는 위치를 구하는 과정

    - 시작 위치=1, 끝 위치=6 으로 설정
    - 시작 위치 1과 끝 위치 6의 중간위치인 3번째 값과 8을 비교
    - 5는 8보다 작으므로 시작위치를 4로 설정 후 재귀
    - 시작위치 4와 끝 위치 6의 중간인 5번째 값과 8을 비교
    - 9는 8보다 크다. 하지만 이때! 이분 탐색과 달리 끝 위치를 중간 위치인 5로 설정한다.
    - 시작 위치=4, 끝 위치=5 이므로 중간위치인 4번째값과 8을 비교
    - 7은 8보다 작다. 따라서 시작위치인 중간위치+1=5로 설정
    - 시작위치=끝위치=5이므로 5번째 값인 9가 lower bound가 된다.
    
```c

#include <stdio.h>

int lower_bound(int[], int, int);

int main()
{
	int arr[10] = {1, 3, 4, 5, 7, 9, 12, 13, 15, 18}; // 데이터들이 크기순으로 졍렬되어 있는 상태이다.
	int target = 10; // 이 중 몇 번째 인덱스부터 10 이상이 되는지 찾아보도록 하자.
	int n = 10; // 배열의 크기
	printf("lower bound is arr[%d]\n", lower_bound(arr, target, n));
	return 0;
}

int lower_bound(int arr[], int target, int size)
{
	int mid, start, end;
	start = 0, end = size-1;

	while (end > start) // end가 start보다 같거나 작아지면, 그 값이 Lower Bound이므로 반복을 종료한다.
	{
		mid = (start + end) / 2; 
		if (arr[mid] >= target) // 중간값이 원하는 값보다 크거나 같을 경우, 끝값을 중간값으로 설정하여 다시 탐색한다.
			end = mid;
		else start = mid + 1; // 중간값이 원하는 값보다 작을 경우, 시작값을 중간값+1로 설정하여 다시 탐색한다.
	}
	return end;
}


// 결과값 : lower bound is arr[6]=12 
```




## Upper Bound

- 원하는 값 k를 초과한 값이 처음 나오는 위치를 찾는 과정
- lower bound의 arr[mid]를 target과 비교하는 부분에서 등호만 없애면 된다.


```c

#include <stdio.h>

int upper_bound(int[], int, int);

int main()
{
	int arr[10] = {1, 3, 4, 5, 7, 9, 12, 13, 15, 18}; // 데이터들이 크기순으로 졍렬되어 있는 상태이다.
	int target = 3; // 이 중 몇 번째 인덱스부터 3 초과가 되는지 찾아보도록 하자.
	int n = 10; // 배열의 크기
	printf("Upper bound is arr[%d]\n", upper_bound(arr, target, n));
	return 0;
}

int upper_bound(int arr[], int target, int size)
{
	int mid, start, end;
	start = 0, end = size-1;

	while (end > start) // end가 start보다 같거나 작아지면, 그 값이 Upper Bound이므로 반복을 종료한다.
	{
		mid = (start + end) / 2; 
		if (arr[mid] > target) // 중간값이 원하는 값보다 클 경우, 끝값을 중간값으로 설정하여 다시 탐색한다.
			end = mid;
		else start = mid + 1; // 중간값이 원하는 값보다 작거나 같을 경우, 시작값을 중간값+1로 설정하여 다시 탐색한다.
	}
	return end;
}

// 결과값 : upper bound is arr[2]

```
