# Lazy Variables 
```swift
    lazy var stackView: UIStackView = {
        let stackView = UIStackView()
        some Code... 
        
        return stackView
    }()
```
- Swift UIKit에서 UI Component를 코드로 선언할 때 위와 같이 `Lazy`를 사용하는 경우를 심심치 않게 볼 수 있는데...
- 어떤 이점이 있길래 특정 컴포넌트를 선언할처 때 `Lazy` 키워드를 써고 언제 어떻게 적절히 사용해야될지 알아보려고 합니다. 


## 정의

```markdown
"A lazy stored property is a property whose initial value is not calculated until the first time it is used"
```
- 애플 공식문서를 참고하면 '**처음으로 사용되기 전까지 연산 작업이 되지 않는 `저장 프로퍼티`**' 라고 직역 할 수 있겠습니다.
- 즉 `Lazy Stored Property`는 인스턴스가 초기화 되는 시점이 아니라 속성에 처음 접근하는 시점에 초기화 되는 것으로 이해할 수 있습니다.

## 사례
보다 쉽게 이해하기 위해 하나의 사례로 설명해보겠습니다. <br>

<center>
<img src="https://user-images.githubusercontent.com/75591730/163290693-090258b5-71ea-4663-885f-c3e4ee1c8a34.jpeg"> <br>
</center>
카카오톡에서 상대방의 프로필 사진을 클릭하면 위 같은 스크린샷을 확인할 수 있는데요. 오른쪽 상단의 `Image Button`은 마지막으로 유저가 업로드한 이미지를 보여주고 클릭 시 아미지 히스토리를 볼 수가 있습니다. 근데 최근 이미지를 보려고 해당 버튼을 클릭했을 때, 종종 버튼의 이미지와 다른 이미지가 보여지는 경우가 있는데요. <br>
이런 경우는 해당 `Image Button`이 Lazy로 선언되었기 때문이라고 추측해볼 수 있겠습니다. 그래서 이전에 삭제한 전 애인과의 사진이 불특정 다수에게 보여지는 경우가 있죠😂<br>

이런 불상사가 있지만 이렇게 Lazy로 저장 프로퍼티를 선언한 이유는 불필요한 메모리 차지를 방지하기 위해서 입니다. 만약 Lazy로 선언하지 않았다면 그냥 단순히 프로필 이미지를 클릭했을 때, 이전 과거의 프로필 이미지 히스토리를 업로드 해야되고 이렇게되면 쓸데 없이 메모리만 차지하게 되고 딜레이가 생길 수 있기 때문입니다.<br>

즉 프로필 이미지`(인스턴스)`가 화면에 초기화 되는 시점이 아니라 유저가 프로필 이미지 히스토리를 보기 위해 버튼을 클릭 했을 때`(속성에 접근)` 서버로부터 데이터를 받아 화면에 업데이트하는 접근방식을 취하고 있다고 이해할 수 있겠습니다.

## 코드
결국 Lazy Variables를 사용하는 이유는 무건운 작업을 지연시키기 위함입니다 `(Delay Expensive Task)`. 코드로 살펴보겠습니다. 
```swift 
struct ExpensiveTask {
    // Loop을 이용해 연산이 많이 필요한 무거운 Function 재현
    static func loadProfileImageHistory() -> Int {
        var images: [Int] = []
        for i in 1...4000 { images.append(i) }
        return images.last!
    }
}

struct UserProfile {
    var name: String
    var birhY: Int
    var showProfileHistoryImage = ExpensiveTask.loadProfileImageHistory()
    lazy var showProfileInfo = {
        return "프로필 닉네임은 \(name)이고 \(String(birhY))에 태어났습니다"
    }()
}

var porfile1 = UserProfile(name: "제스퍼", birhY: 1994)
print(porfile1.showProfileInfo)
```
- `UserProfile` 구조체에는 기본적인 유저의 정보와 몇 가지 메소드를 포함하고 있습니다. 
- 이때 `showProfileHistoryImage` 메소드는 연산이 많이 필요한 메소드 입니다.


<img src="https://user-images.githubusercontent.com/75591730/163296219-c4a750ec-5117-419d-99e6-fe26c1fae2dd.gif" width="580"><br>

- 만약 위 코드 처럼 연산이 무거운 메소드를 일반 변수를 선언했다면, 실제 기능에서는 필요 없지만 작업이 무거운 구조체의 인스턴스를 초기화는데 시간이 많이 걸리는걸 확인할 수 있습니다. 

```swift
lazy var showProfileHistoryImage = ExpensiveTask.loadProfileImageHistory()
```
- 하지만 일반 변수가 아니라 `Lazy` 키워드를 적용하게 되면 인스턴스 초기화 과정에서 해당 메소드에 접근하지 않기 때문에 딜레이를 줄일 수 있습니다. 


 
## 고려사항
아래와 같이 Lazy variables을 선언하려면 몇 가지 고려사항이 존재합니다.
1. lazy는 반드시 var와 함께 쓰여야 함
2. 기본적으로 lazy는 struct와 class에서만 사용할 수 없음.
3. omputed Property에는 lazy 키워드를 사용할 수 없음.
4. lazy에 어떤 특별한 연산을 통해 값을 넣어주기 위해서는 코드 실행 블록인 closure를 사용함.
(보충 필요)


## 요약
- Lazy Variable을 쓰는 이유
  - To Delay Expensive Task
    - And Save Some Memory 
    
- Lazy 키워드를 사용할 때 고려 사항 존재 



