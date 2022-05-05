## Handling Float Problems
float을 사용할 때 고려해야되는 요소들이 많다보니 레이아웃 문제가 많이 발생하는데 이때 해결할 수 있는 접근방법이 아래와 같이 크게 2가지가 있다.
- overflow
- clear fix

## 문제 상황
float 처리가된 3개의 `float box`와 긴 문단을 가지고 있는 `inline-box`가 위 아래로 나누어져 배치되어야 한다고 가정해보자. <br/>
  
<img width="1058" alt="aim3" src="https://user-images.githubusercontent.com/75591730/166874580-1b560975-3e63-4065-9b75-8e886b7fb3ce.png">
<img width="1061" alt="32" src="https://user-images.githubusercontent.com/75591730/166876334-d9e0f8f7-ecf9-49cd-b42a-9d0d1295f902.png">
HTML

```html
  <div class="box">
      <div class="float red">Float</div>
      <div class="float yellow">Float</div>
      <div class="float blue">Float</div>
  </div>
   <div class="other">
      <p>          
        La République En Marche ![a] (frequently abbreviated LREM, LaREM or REM;
        translatable as The Republic On The Move, Republic Forward, or The
        Working Republic),[3][4][5] sometimes called simply En Marche ! (French:
        [ɑ̃ maʁʃ])[6] as its original name, is a liberal[7][8] political party in
        France. The party was founded on 6 April 2016 by Emmanuel Macro.
        former Minister of the Economy, Industry and Digital Affairs, who was
        later elected President of the French Republic in the 2017 presidential
        election with 66.1% of the second-round vote. Presented as a
        pro-European party,[9][10][11] Macron considers LREM to be a progressive
      </p>
    </div>
```
CSS 
```css 
 .box {
  margin: 0px auto;
  width: 200px;
}

.float {
  height: 100px;
  width: 100px;
  float: left;
}

.red {
  background-color: red;
}

.yellow {
  background-color: yellow;
}

.blue {
  background-color: blue;
}

.other {
  background-color: black;
  color: white;
}


## Float With OverFlow
- 여기서 float 자식들을 가지고 있는 부모 box에 이때 `overflow:hidden`을 주게되면 부모가 float-box의 `부모box`가 특정 영역(높이)을 가지게 됨.

```css 
.box {
  margin: 0px auto;
  width: 200px;
  overflow: hidden;
 }
```


           



