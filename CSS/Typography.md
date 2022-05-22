# Typography

<img src="https://user-images.githubusercontent.com/75591730/167326014-83663091-774d-4354-809b-8331da62b959.jpg">
웹프로그래밍에서 `Typography`란 웹 사이트 내에서 사용되는 텍스트의 레이아웃(배열)과 스타일 규칙을 의미함.


1. fontsize
```css
p {
    font-size: 14px;
} 
```
폰트 사이즈를 사용할 때, 아래와 같이 3가지 단위가 존재 
- px
- em
- rem

px을 값이 고정되어 있는 `절대 단위(Absolute unit)`이지만 em, rem은 상대적으로 값이 변하는 `상대단위(Relative unit)`임.


2. line-height (줄 간격)
```css
.text {
    font-size: 16px;
    line-height: 1.5;
}
```
<img width="947" alt="먀ㅡ" src="https://user-images.githubusercontent.com/75591730/167327900-c33effcf-720d-40b1-a06f-e3f1b56b352b.png">
Texxt 는 lingheight 줄 간격에 가운데에 배치가 됨.

3. letter-spacing (줄 간격)
```css 
    letter-spacing = -0.01em; 
```
- `em` 단위를 주로 사용


4. font-family
폰트 서체를 표현할 때 사용
```css
    .text {
    font-family: "PSL Ornanong Pro";
    font-family: "PSL Ornanong Pro", sans-serif;
    font-family: "PSL Ornanong Pro", "Roboto", sans-serif;
}
```
- 서체가 없는 경우를 대비해서 다음이 선택될 서체를 나열해서 지정할 수 있음. (폴백 폰트)
- 참고로 sans-serif는 삐침이 없는 폰트라고 이해할 수 있음. Ex) 한글 돋음

5. font-weight
폰트의 굵기를 표현할 때 사용
```css 
    .text {
        font-weight : 400;
    }
```
<img width="437" alt="bold" src="https://user-images.githubusercontent.com/75591730/167328423-0889b14e-a488-4a30-82ab-585d683f0355.png">
- 400은 regular , 700은 bold를 의미함.
