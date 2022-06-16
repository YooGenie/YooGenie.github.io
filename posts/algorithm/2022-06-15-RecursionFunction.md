---
title:  "재귀함수" 
excerpt: "재귀함수를 이해하고 예시로 공부하자"

toc: true
toc_sticky: true

date: 2022-06-15
last_modified_at: 2022-06-16
---

# 재귀함수
자기 자신을 호출하는 함수

# 재귀 사용 예시
* 유클리드 호제법 => 최대공약수, 최소공배수 
* 피보나치 수열

<br>
<span style="color:gray;">공무원 시험 준비할 때 코드를 보고 결과값을 도출하는 문제가 많이 나왔다.</span><br>
<span style="color:gray;">두가지의 예시를 코드를 짜보자!</span>

## 최대공약수 예시
```go

func GreatestCommonFactor(m int, n int) (result int) {

	if n == 0 {
		fmt.Println(m)
		return m
	}
	return GreatestCommonFactor(n, m%n)

}

func main() {
	GreatestCommonFactor(51, 15)
}

```
나는 계속 for문을 돌려야한다고 생각했다. 근데 재귀함수를 이용하면 더 간단하게 해결이 됐다.

### 참조 이슈
https://github.com/YooGenie/algorithm/issues/132

## 최소공배수






