# LIS (Longest Increasing Subsequence) 알고리즘


## 참고 사이트

- https://jason9319.tistory.com/113
- https://seungkwan.tistory.com/8

## LIS란?

- 가장 긴 증가하는 부분 수열
- ex) 

  - ![LIS예제1](./images/LIS예제1.PNG)
  - 다음과 같은 수열이 존재한다면, 빨간 부분으로 색칠한 부분이 LIS가 된다.
  
  - ![LIS예제2](./images/LIS예제2.PNG)

- 앞에서부터 뒤로 숫자를 선택하며 부분 수열을 구성해 나갈때 증가하는 순서대로 숫자를 고르면서 고른 부분 수열의 길이가 최대 길이가 되도록 숫자를 선택하는 경우

- 구현 방법은 3가지가 있다 : DP 2차원 배열, 세그먼트 트리, 이분탐색


## LIS 시간복잡도

- DP 2차원 배열 : O(N^2)
- 이분탐색 : O(NlogN)



## LIS 접근 방법 (DP 2차원 배열)

- **dP[i]=i번째 원소를 마지막으로 하는 LIS의 길이**
- **dp[i]**=1~i-1까지의 원소들에서 **i번째 원소보다 값이 작은 것들 중에서 가장 큰 dp값 + 1**

```C

#include <iostream>
#include <algorithm>
using namespace std;

int arr[1001], dp[1001], ans, N;
//dp[i] = i번째 원소를 마지막으로 하는 LIS의 길이
int main() {
	ios_base::sync_with_stdio(false);
	cin >> N;
	for (int i = 1; i <= N; ++i) {
		cin >> arr[i];
		int here = 0;
		for (int j = 1; j < i; ++j) {
			if (arr[i] > arr[j])
				here = max(here, dp[j]);
		}
		dp[i] = here + 1;
		ans = max(ans, dp[i]);
	}

	for (int i = 1; i <= N; i++)
		cout << dp[i] << " ";
	cout << "\n";


	cout << ans;
	return 0;
}


```


## LIS 접근 방법 (이분 탐색)

- O(N)의 방법으로 수열을 처음부터 확인할건데 이분탐색을 이용하여 LIS를 유지하기 위한 최적의 위치에다가 수를 삽입하는 방식
- 자리를 찾는데 lower_bound를 이용하기 때문에 최적의 위치를 찾는 데 걸리는 시간복잡도는 O(log N)



**진행중**

https://jason9319.tistory.com/113
https://mygumi.tistory.com/303
https://seungkwan.tistory.com/8

https://www.acmicpc.net/problem/13711


