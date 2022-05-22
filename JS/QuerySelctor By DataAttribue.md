Javascript에서 HTML 요소를 가져오는 방법은 너무 다양해서, 필자처럼  이제 웹을 막 공부하고 있는 사람들은 혼란스러울 수 있는 부분이다.

강의에서도 `"때에 따라 적절하게 사용하시면 됩니다"` 라고만 말하지 특정 방법을 권장하고 있지는 않다.

그래서 Javscrip에서 HTML 요소를 가져오기 좋은 방법이 무엇일지 고민해 보았다.


## Query Selector with CSS Selector
본 포스팅에서 여러 HTML요소를 가져오는 여러 방법 중 `Query Selector`를 이용한 방식을 이야기 해보려고 한다.

가장 최근에 나온 Web API이며 CSS에서 HTML 내 요소를 선택하는 것과 동일한 방식으로 요소를 Javascript안에서 변수에 할당할 수 있다.

```html 
<div class="user-info">
  <span class="user-info name">Ximya</span>
</div>
```

```javascript
const userName = document.querySelector(".user-info.name");
// or
const userName = document.querySelector(".user-info span");
```

## Use `Data Attribute` rather than `CSS Selector`

이렇게 `CSS 선택자`를 통해 요소를 가져와도 되지만 필자는 아래와 같이 `데이터 속성`을 이용한 접근 방식을 선호한다.

```html
<div class="user-info" data-userInfo>
  <span class="user-info name" data-userInfo="name">Ximya</span>
</div>
```

```javascript 
// Data Attribute
const userName = document.querySelector("[data-info="name"]");
```


그럼 `데이터 속성`을 이용해서 얻는 이점은 무엇일까?

### 1. CSS, Javascript 작업분리
Javascript에서 `CSS 선택자`로 요소를 가져왔다고 가정해보자.
이때 요소의 `클래스 명`을 변경해서 CSS의 변화를 주었을 때, Javscript에서도 변경된 `클래스 명`으로 변경해줘야 되는 **번거로운 일**이 생긴다.

하지만 Javascript에서`데이터 속성`으로 요소를 선택했다면 요소의 `클래스 명`이 변경되어도 **전혀 영향을 받지 않게 된다.**

즉 요소의 클래스명이 변경되어도 Javascript에서는 `데이터 속성`으로 요소가 선택 되었기 때문에 CSS 작업에만 신경을 쓸 쑤 있다. 결과적으로 소프트웨어의 복잡성을 낮춘다.


### 2. BEM 코드 컨벤션을 대체
개인적으로 `BEM의 코드 컨벤션`을 좋아하지 않는다.
선택자의 이름을 가능한 명확하게 만들어 개발, 디버깅, 유지보수를 효율을 낼 수 있겠지만 너무 극도로 반복적인 네이밍 규칙이 과연 `깨끗한 마크업`인지 의문이다.

만약 `BEM 코드 컨벤션`의 목표가 **각 요소를 최대한`Semantic`하게 만드는 것**이라면,`데이터 속성`을 요소에 적용하는것이 훌륭한 대체제가 될 수 있다고 생각한다. 클래스 명을 최대한 간결하게 짓고 `데이터 속성`을 통해 요소가 Javascript에서 정확히 어떤 역할을 담당하는지 구분지어 요소 자체를 `Semantic`하게 만드는 것이다. 결과적으로 이런 접근 방식이 협업에 좀 유리하지 않을까 라는 생각도 한다.








