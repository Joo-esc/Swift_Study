# FLoat
## 개념
- Block 요소들을 `가로배치` 하기 위해서 사용되는 속성
- 다만 `flex` 등장으로 layout을 배치할 때는 float 보다는 flex를 사용을 권장하는 추세 

## 특징
- 어떤 타입의 box이단 float속성을 선언하면 `block`타입의 box로 변경됨
  - 다만 block의 `길막`을 하는 형태를 가지고 있지는 않음
    - 여기서 `길막`아래와 같은 의미를 가지고 있음. 
      1) 따로 width를 선언하지 않은 경우, 부모의 content-box의 width가 해당 blcok-box가 width가 되는 것
      2) width을 선언한 block-box의 경우, 남은 공간은 margin으로 자동(auto margin)으로 채워짐
- `길막`을 하지 못하는 block 또는 `영역`을 차지 하지 않는 block이라고 이해할 수 있음.
  - block type이기 때문에 margin, padding 등의 속성 선언 가능
- `영역`을 차지하지 않는 block-box이지만 inline-box 요소들은 float 처리된 box를 인식함. (아래 사진 참고)
  <img width="329" alt="aim3" src="https://user-images.githubusercontent.com/75591730/166868436-e00a5916-94c5-409d-b67a-d877593763d5.png">
  - flot이 적용된 child box들 ==> 영역을 가지고 있지 않음. 하지만 inline-box인 p 태그의 컨텐츠들을 child box를 인식하고 텍스트들이 정렬됨.
  




## 예제로 알아보는 Float
### Float1 

<img width="362" alt="float1" src="https://user-images.githubusercontent.com/75591730/166864468-7fc4e132-2354-44af-91a1-89a73fdd2d61.png">

```html
    <div class="box">
      <div class="float float1">One</div>
      <div class="float float2">Two</div>
      <p>The two boxes should float to either side of this text.</p>
    </div>
```

```css
.float {
  height: 100px;
  width: 100px;
  padding: 20px;
}

.box {
  margin: 20px auto;
  width: 300px;
}

.float1 {
  background-color: red;
  float: left;
}

.float2 {
  background-color: yellow;
  float: right;
}

p {
  width: 100px;
  height: 100px;
  display: inline-block;
  padding: 4px;
}
```

### Float2
<img width="355" alt="float2" src="https://user-images.githubusercontent.com/75591730/166865380-33afa465-3426-4a84-bc99-a9c88d615697.png">

```html 
   <div class="box">
      <div class="float">Float</div>
      <p class="upper">This sentence appears next to the float.</p>
      <p class="below">Cause this sentence to appear below the float.</p>
    </div>
```
```css
.box {
  width: 300px;
  padding-top: 20px;
  margin: 0px auto;
}

.float {
  height: 100px;
  width: 100px;
  padding: 20px;
  float: left;
  margin-right: 20px;
  background-color: aqua;
}

.below {
  float: left;
}

```
### float3
<img width="398" alt="aim" src="https://user-images.githubusercontent.com/75591730/166866830-cdff1d22-322a-4563-ac74-34098f003cc4.png">

```html
 <div class="box">
    <div class="float">Float</div>
    <p>This sentence appears next to the float.</p>
</div>
```

```css 
.float {
  float: right;
  height: 80px;
  width: 80px;
  background-color: aquamarine;
}

.box {
  background-color: skyblue;
  width: 300px;
  height: 60px;
  padding-right: 20px;
}

```

