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
#include <vector>
#include <algorithm>

using namespace std;

vector<int> v(1001);
vector<int> dp(1001);

int main() {

	int n;
	cin >> n;

	for (int i = 1; i <= n; i++)
		cin >> v[i];

	dp[1] = 1;
	for (int i = 1; i <= n; i++) {
		int max_value = 0;
		for (int j = 1; j < i; j++) {
			if (v[j] < v[i]) {
				max_value = max(max_value, dp[j]);
			}
		}
		dp[i] = max_value+1;
	}

	int max_result = 0;
	for (int i = 1; i <= n; i++)
		if (dp[i] > max_result)
			max_result = dp[i];
	cout << max_result << "\n";
	return 0;
}

```

## LIS 접근 방법 (세그먼트 트리) O(N log N)

- arr[x]의 위치에 x번째 수를 마지막 원소로 가지는 lis의 길이를 업데이트
- 매 순간마다 자기보다 작은 구간에 최대값을 찾는 쿼리를 날려 최대값+1을 업데이트 하는 방식
- N번을 확인하는 데 최대값을 찾는 데 O(log N)이 걸리니 총 O(N log N)



## LIS 접근 방법 (이분 탐색) O (N log N)

- O(N)의 방법으로 수열 확인, 이분탐색을 이용하여 최적의 위치에 수를 삽입하는 방식
- 자리를 찾는데 lower_bound 사용 - O(log N)

	- 최적의 위치 찾는 방법
		- 벡터를 하나 생성한 뒤 -INF (나올 수 없는 값) 삽입
		- 이후 매번 수열을 볼 때마다 




## 관련 문제

https://www.acmicpc.net/problem/13711


