# UICollectionView
>  UICollectionView의 기본적인 동작 원리에 대해 알아보려고 합니다. (추후 CollectionView의 CustomLayout 내용 업데이트 예정)

## 정의
```swift
class SomeCollectionView: UICollectionView {
    // Nothing todo
}
```
- 앱에서 특정 데이터의 목록을 여러 방식으로 보여줄 수 있는데 Swift UIkit에서는 주로 `UICollectionView`와 `UITableView`을 사용합니다.
- `UITableView`와 전체적인 포맷은 비슷하지만 `UICollectionView`는 유연하고 변경 가능한 Layout을 사용하여 데이터를 화면을 다채롭게 보여줍니다.

## UICollectionView와 UITableView
UICollectionView와 UITableView을 비교하며 알아봅니다.

<center>
<img src="https://user-images.githubusercontent.com/75591730/163917251-cdda1466-2d40-4836-981d-f3e1f75644d2.jpeg" width="240">
<img src="https://user-images.githubusercontent.com/75591730/163917427-1ac3f5a6-678d-4eb9-9b87-b14d10f395b9.jpeg" width="240">
</center>
<center>UICollectionView(왼쪽) / UITableView(오른쪽) </center> 
<br>

위 사진으로 `UICollection`과 `UITableView`의 차이를 확인해볼 수 있습니다.

두 View 모두 데이터 목록을 화면에 보여주는 공통점이 있지만 뷰가 나타나는 `레이아웃` 에서 차이점이 존재합니다.
- `UITableView` : 단일 열(Column)에서 여러 행(Row)으로 데이터를 보여줌. 수직 스크롤만 가능. 
- `UICollectionView`: 일반적으로 그리드 레이아웃을 구성하는데 많이 사용. 그 외 CustomLayout을 사용해 다채로운 뷰의 형태로 그려짐.

`UICollectionView`는 그리드와 스택, 타일 그리고 원형을 포함하여 다양한 유연성을 제공하는 인터페이스라고 이해할 수 있겠습니다.


## 구성요소
<center>
<img src="https://user-images.githubusercontent.com/75591730/163919919-66160a9a-3685-4100-a824-b99895892b1e.png" width="600">
</center> <br>
<center> 콜렉션 뷰 관계도 </center>

UITableView처럼 DataSource, Delegate 객체를 기반으로 데이터를 받아 뷰를 그리고 동작을 관리합니다. <br>
가장 큰 차이점은 앞서 계속 말씀드린것 처럼 `Collection View Layout`의 유무입니다.
위 관계도를 보면 데이터 레이어와 프레젠테이션 레이어가 분리되어 있고 `레이아웃으로 뷰의 배치를 결정` 하는 흐름을 확인할 수 있습니다.

### Collection View Layout 
그럼 여기서 말하는 `Layout` 뭔지 알아봅시다. <br>
UICollectionView에서 뷰의 배치를 결정하기 위해서는 `CollectionViewLayout`이 필요한데 이때 주로 `CollectionFlowLayout`을 활용합니다(CollectionViewFlowLayout은 애플이 제공하는 UICollectionVIew의 한 유형).<br> 
다른 Collection Layout 클래스도 존재하지만 애플은 가능하면 `CollectionFlowLayout` 사용을 권장하고 있습니다. 

### Collection Flow Layout
<center>
<img src="https://user-images.githubusercontent.com/75591730/163922270-631aa657-8ada-4749-af93-3a7813bc5f3b.png" width="600">
</center>
<center> CollectionView 흐름도 (수직 스크롤일 경우) </center>
Flow Layout은 스크롤의 방향에 따라 선을 기반으로 가능한 많은 셀을 배치하고 넘어갑니다. <br>

- Flow Layout 설정 순서
  1. FlowLayout객체를 만들고 Collection View에 할당
  2. 셀의 너비와 높이를 설정
  3. 필요하다면 item이나 line의 간격을 설정
  4. Section Header, Footer가 설정되어 있다면 필요한 사이즈로 설정
  5. 레이아웃의 스크롤 방향을 설정 (기본 값은 vertical)

    
## 코드
> 코드를 통해 UICollectionVIew 와 UICollectionViewFlowLayout을 살펴보겠습니다.

### Cell 사이즈 설정

1) 고정 Cell Size 설정
```swift        
let layout = UICollectionViewFlowLayout()
layout.itemSize = CGSize(width: 100, height: 100) // 고정 Cell Size 설정        
```
- `flowLayout`에 CGSize를 할당

2) 동적인 Cell Size 설정 (메소드)
```swift
    func collectionView(_ collectionView: UICollectionView, layout collectionViewLayout: UICollectionViewLayout, sizeForItemAt indexPath: IndexPath) -> CGSize {
    // ViewController의 전체 넓이를 기준으로 Cell 사이즈값 설정
        let size = (view.frame.width - 42) / 2 
        return CGSize(width: size, height: size)
    }
```
- 동적으로 사이즈가 필요하다면 `UICollectionViewDelegateFlowLayout`을 준수하여 메서드를 구현 


### Spacing 설정
<center>
<img src="https://user-images.githubusercontent.com/75591730/163947975-bb82b646-0139-467b-ba2c-3f73dd6a7c6e.png" width="400">
</center><br>

- 최소 간격을 설정할 수 있으며 Leading과 Trailing 쪽은 간격이 생기지 않음

1) 고정 Spacing 설정
```swift
let layout = UICollectionViewFlowLayout()
layout.minimumLineSpacing = 20  
```

2) 동적 Spacing 설정
```swift
collectionView(_:layout:minimumLineSpacingForSectionAt:) 
```



