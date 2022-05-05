# BoxType

## 개념
- 모든 HTML 요소는 `Box`형태의 영억을 가지고 있고 각 `Box`는 여러 타입으로 나누어져 있음
- Box Type은 `display`속성으로 정의.


## 1. Block 
- 길막. 다른 box 요소들이 옆에 못오도록 막는 속성이라고 이해할 수 있음.
- 별도의 width를 선언하지 않은 경우, 해당 box의 width는 부모 content-box의 전체 넓이 차지함.
- 반대로 width를 선언한 경우, 남은 공간은 margin으로 채워지게 됨.
- 부모의 height 설정하지 않을 경우, 자식 요소의 총합이 부모의 height이 됨.

```html
// HTML
  <div class="parent">
      <div class="child1">child1</div>
      <div class="child2">child2</div>
    </div>
```
```css 
// css
.parent {
background-color: blueviolet;
}

.child1 {
background-color: aqua;
display: block;
height: 100px;
width: 200px;
}

.child2 {
background-color: bisque;
display: block;
height: 100px;
width: 140px;
}
```

<img width="445" alt="block" src="https://user-images.githubusercontent.com/75591730/166855424-1bd17f59-05bd-42b1-badc-a65a9548a0d9.png">


___ 

## Inline
- block box는 옆에 다른 요소가 배치되는 것을 제한했다면 `inline box`는 흐름에 맞게 다른 요소들을 배치할 수 있는 타입이라고 이해할 수 있음.
<img width="320" alt="ilnine_ex" src="https://user-images.githubusercontent.com/75591730/166855990-b3ed04da-dca5-419f-b319-02d7f86c5feb.png">
- 위 사진처럼 옆에 box 요소들이 `흐름`에 맞게 채워지는 box 형태라고 이해할 수 있음.
- block box는 영역을 고려하는 타입이라면 `inline box`는 흐름을 고려.
  - 그렇기 때문에 width, height, padding-top, padding-bottom, border-top, border-bottom, margin-top, margin-bottom 같은 속성을 사용할 수가 없음
    - inline의 흐름을 방해하기 때문
<img width="1044" alt="padding" src="https://user-images.githubusercontent.com/75591730/166856718-d9cbcbc9-122c-4a5a-95ec-914992b374fd.png">


```html
    <p>
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book. It has survived not only five centuries, but
      also <span>하이라이트 문구</span>
      unchanged. It was popularised in the 1960s with the release of Letraset
      sheets containing Lorem Ipsum passages, and more recently with desktop
      publishing software like Aldus PageMaker including versions of Lore
    </p>
```

```css
span {
  background-color: blueviolet;
  padding: 73px;
  margin-bottom: 1000px;
}
```
___

## Inline Block
- block 과 line 속성이 모두 포함된 type

```html
  <p>
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book. It has survived not only five centuries, but
      also <span>하이라이트 문구</span>
      unchanged. It was popularised in the 1960s with the release of Letraset
      sheets containing Lorem Ipsum passages, and more recently with desktop
      publishing software like Aldus PageMaker including versions of Lore
    </p>
```

```css 
span {
  background-color: blueviolet;
  height: 40px;
  display: inline-block;
}
```
<img width="838" alt="aim2" src="https://user-images.githubusercontent.com/75591730/166857345-0c645c19-30d5-496f-a0f3-a5466c8fe418.png">




