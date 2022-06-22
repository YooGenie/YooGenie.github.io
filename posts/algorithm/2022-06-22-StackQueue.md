---
title:  "스택,큐" 
excerpt: "스택,큐를 이해하고 예시로 공부하자"
date: 2022-06-22
last_modified_at: 2022-06-22
---

# 스택
* LIFO (last-in-first-out)
* 마지막에 들어온 값을 먼저 꺼낸다

```go
const max = 5
var top = 0
var st [max]int

func StackMain() {
	stackInit()
	pop()
	push(5)
	pop()
	push(3)
	push(9)
	push(1)
	push(9)
	push(8)
	push(4)
	pop()
}

func stackInit() {
	fmt.Println("stack 초기화 시켰습니다")
	top = 0
}

func Empty() bool {
	return top == 0
}

func Full() bool {
	return top == max
}

func push(x int) {
	if Full() {
		fmt.Println("stack 꽉 찼습니다.")
		return
	}
	st[top] = x
	fmt.Println(st[top], "를 push 했습니다")
	top++
}

func pop() {
	if Empty() {
		fmt.Println("stack 비어있습니다")
		return
	}
	top--
	fmt.Println(st[top], "를 pop했습니다")
}

```

### 참고 이슈
https://github.com/YooGenie/algorithm/issues/138

# 큐
* FIFO(first-in-first-out)
* 먼저 들어온 값을 먼저 꺼낸다

