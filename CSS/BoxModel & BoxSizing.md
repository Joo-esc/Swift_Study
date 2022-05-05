# BoxModel

## 개념
<img src="https://user-images.githubusercontent.com/75591730/166688213-fc41dfb0-2211-40f8-ac60-1c2d2af50383.png"><br/>
- 모든 HTML 요소는 `Box`형태의 영억을 가지고 있음.
- `Box`content, padding, border, margin으로 구성됨

| 속성      | 설명                                                                                                                         |
|---------|----------------------------------------------------------------------------------------------------------------------------|
| content | 요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역. width, height 프로퍼티를 갖음.                                                                    |
| padding | 테두리(Border) 안쪽에 위치하는 요소의 내부 여백 영역. padding 프로퍼티 값은 패딩 영역의 두께를 의미하며 기본색은 투명(transparent). 요소에 적용된 배경의 컬러, 이미지는 패딩 영역까지 적용되. |
| border  | 테두리 영역으로 border 프로퍼티 값은 테두리의 두께를 의미                                                                                        |
| margin  | 바깥 여백으로 요소와 요소 사이에 간격을 나타냄. 기본적으로 투명(transparent)하며 배경색을 지정할 수 없음                                                          |

- margin, padding 속성을 적용하면서 content값을 box의 사이즈를 유지하려면 `box sizing` 속성을 적용해야됨.
  - contentbox가 아니라 `borderbox`를 기준으로 사이즈를 잡는가 이해할 수 있음.
```css 
* {
    box-sizing: border-box;
}
```
- 보통 css 코드를 작성할 때 전체선택자로 box-sizing을 일괄 적용함

## 코드
html
```html
  <body>
<div class="box">content</div>
<div class="box1">content</div>
</body>
```

css 
```css
.box {
  height: 100px;
  width: 100px;
  background-color: aquamarine;
  border: 10px solid rebeccapurple;
  box-sizing: border-box;
  padding: 2px 10px 10px 20px;
}

.box1 {
  height: 100px;
  width: 100px;
  background-color: aquamarine;
  border: 10px solid rebeccapurple;
  margin-top: 20px;
  box-sizing: border-box;
}
```

## 구현물
<img width="254" alt="box" src="https://user-images.githubusercontent.com/75591730/166716342-b50495b1-dad4-44da-82c2-032bd6aa4f22.png">


