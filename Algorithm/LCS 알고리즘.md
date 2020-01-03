# LCS (Longest Common Subsequence) 알고리즘

## 참고 사이트

- https://twinw.tistory.com/126


## LCS란?

- LCS : 최장 공통 부분 문자열
	> substring / subsequence
	> substring : 연속된 부분 문자열
	> subsequence : 연속적이지 않은 부분 문자열

	ex) lamhungry
	- substring : mhun
	- subsequence : mugy


## LCS 용도

- 염기서열 유사성 분석에 사용된다.
- 이외에도 음파 단어 검색 및 교정 등에 사용


## LCS 시간복잡도

- 문자열의 길이가 n, m일 때 시간복잡도는 O(nm)


## LCS 알고리즘 접근 방법

- DP(Dynamic Programming)으로 특정 범위까지의 값을 구하고 다른 범위까지의 값을 구할 때 이전에 구해 둔 값을 이용하여 효율적으로 문제를 해결


- ex) 문자열'ACAYKP'와 'CAPCAK'
- 우선 하나의 String을 기준 String, 다른 String을 비교 String으로 둔다.

  - ![LCS_예제1](./images/LCS_예제1.PNG)


