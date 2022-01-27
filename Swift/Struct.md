# Struct

Swift에서는 `struct` 와 `class` 가 공존. 데이터를 용도에 맞게 블록 형태로 표현할 때 용이하게 사용됨.

`struct`는 Swift에서 `first class citizen` (일급 시민 객체)로 여겨짐. 즉 프로퍼티 메소드 등의 사용해서 구조화된 데이터와 기능을 가질 수 있음.

```swift
struct 구조체 이름 {
		프로퍼티 & 메서드 // struct 블록 안에 프로퍼티와 메서드를 정의
}
```

- 프로피터 & 메서드를 `struct` 구조체의 멤버 변수라고 정의하기도 함

## 예시

```swift
struct User {
		var nickName: String
		var age: Int
}
```

- `struct`를 사용하기 위해서는 인스턴스를 생성해 주어야함
- **인스턴스**를 생성한다는 것은 `struct` 구조체를 사용하기 위해서 메모리를 생성한다는 것.
    - 메모리에 생성된 `class`와 `struct` 실체라고 이해할 수 있음

### 인스턴스 생성

```swift
var user = User(nickName: "Jerry" , age: 39)
```

- 프로퍼티를 초기화, 자동적으로 생성자(Default Initializer)가 만들어짐.



### 프로퍼티 접근 / 변경

```swift
user.nickName // Jerry
user.nickName = "James" // James
```

- 인스턴스 이름과 프로퍼티를 이름을 점으로 연결해주면 됨.

### 메소드도 동일하게 정의 가능

```swift
struct User {
		var nickName: String
		var age: Int

		func information() {
		print("\\(nickName) \\(age)"
	}
}

```

- 메소드도 프로퍼티와 동일한 방식으로 호출됨
