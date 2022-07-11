---
title:  "싱글톤 패턴"
excerpt: "싱글톤 패턴 공부하자"
date: 2022-07-11
last_modified_at: 2022-07-11
---

# 싱글톤 패턴
- 하나의 클래스에 오직 하나의 인스턴스를 가지는 패턴
  ex) DB연결 모듈
- 하나의 인스턴스를 만들어서 다른 모듈들이 공유한다. 예를 들어서 DB 연결하는 모듈 하나 만들어서 그걸 여러개 API 호출하는 함수들이 사용할 수 있다.

## 단점
1) 의존성이 높아진다 => 모듈간에 결합을 강하게 만든다
- 해결책: 의존성 주입을 통해서 모듈간에 결합을 느슨하게 만들 수 있다

2) 단위테스트 할 수 없다 => TDD를 할 수 없다
- TDD는 주로 단위 테스트로 되어있다.
- 단위 테스트는 테스트가 서로 독립적이어야 테스트를 순서 상관없이 실행 할 수 있다
  (그래서 현재 우리는 통합테스트만 하는걸까?)

## 장점
- 인스턴스 비용이 줄어든다

## 실무에서 사용하는 싱글톤 패턴
```go
var (
	donationServiceOnce     sync.Once
	donationServiceInstance *donationService
)

func DonationService() *donationService {
	donationServiceOnce.Do(func() {
		donationServiceInstance = &donationService{}
	})

	return donationServiceInstance
}

type donationService struct {
}
```
