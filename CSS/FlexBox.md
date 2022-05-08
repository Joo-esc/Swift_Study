# Flex Box
- 정렬의 끝판왕..!
  - 가로 정렬 & 세로 정렬
  - 한 방향에 모두 정렬 & 사이즈에 맞게 정렬
- Float의 단점을 보완한 태그로 최근에는 Float보다는 FlexBox가 주로 사용되는 추세


## 개념
1. 어디에 속성을 적용?
```css
.flexBox {
    display: flex;;
}
```
- 정렬을 하고자하는 요소를 감싸고 있는 부모 요소에 `display : flex` 속성을 적용.

2. 어느 방향에 정렬? <br>
```css  
.flexBox {
    display: flex;
    felx-direction: row; // 가로
}
```
- 가로 또는 세로 방향정으로 설정할지 정의
- 정렬 순서도 지정할 수 있음. (row-reverse, column-reverse)

3. Axis (축)  
<img src="https://user-images.githubusercontent.com/75591730/167264821-c4472335-0db8-4808-b03f-290689294077.png">
Flex Direction을 사용하여 레이아웃을 구성할 때 두 가지 `Axis` 를 기준으로 요소들이 정렬됨.
   - Main Axis : 정렬 기준 축 
     - 디폴트 값인 `flex-direction: row`가 적용된 상태면 가로 방향이 Main Axis가 됨.
   - Cross Axis : Main Axis와 수직이 되는 방향의 축 

4. Flex Wrap
```css 
.flex-box {
    flex-wrap: nowrap;
} 
```
- 어떻게든 한 방향에 모든 요소를 정렬할지 또는 상황에 따라서 여러 요소를 정렬할지를 정의하는 요소
- 즉 감싸지(wrap) 않고 자식의 사이즈를 줄여서라도 한 방향으로만 요소들을 정렬 할 때 `flex-wrap : norap`속성이 필요함.
  - 반대의 경우 `flex-wrap : wrap` 속성으로 정의
  

5. justify-content & align-item & align-content
`Main Axis` 또는 `Cross Axis`를 기준으로 특정 정렬이 필요할 때 사용하는 속성.
- justify-content (mainAxis 기준)
  - flex-start(왼쪽 정렬)
  - flex-end(오른쪽 정렬)
  - center(가운데 정렬) 
  - space-between (각 요소의 간격을 동일하게)
  - space-around (각 요소의 양 옆 or 위 아래 간격을 동일하게)
  
- align-items (crossAxis 기준)


- align-content
  - flex-wrap: wrap 상태 일 때, 즉 cross Axis가 하나 이상 일 때 `align-content` 사용
  - align-content는 부모의 영역을 기준의 cross Axis으로 정렬된다고 이해할 수 있음. 


## 간단 실습

1.
<img width="824" alt="same" src="https://user-images.githubusercontent.com/75591730/167286379-23b9124b-f488-48bc-8574-6531a7e2cc1e.png">

HTML
```html
 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="style.css" />
  <title>Document</title>
</head>
<body>
<div class="card">
  <img src="./images/user.jpeg" alt="profileImage" />
  <div class="card-content">
    <div class="card-content-wrapper">
      <h3 class="card-content-title">
        RE: 안녕하세요 배송 관련 문의드립니다
      </h3>
      <span class="card-content-sender">customer support</span>
    </div>
    <span class="card-content-description"
    >안녕하세요 심야님. 문의 드린 사항에 대한 답변 드립니다. 지난 12일
          전에 배송이 완료되었지만,
        </span>
  </div>
</div>
</body>
</html>
```

```css 
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Spoqa Han Sans", sans-serif;
  list-style: none;
}

html {
  font-size: 16px;
  font-family: "Spoqa Han Sans", sans-serif;
  letter-spacing: -0.03em;
  color: #212529;
}

body {
  background-color: lightslategray;
  padding: 100px;
}

.card {
  height: 120px;
  width: 530px;
  background-color: white;
  display: flex;
  padding: 20px;
}

.card img {
  height: 44px;
  width: 44px;
  border-radius: 50%;
}

.card-content {
  margin-left: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-content-title {
  font-size: 16px;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: -0.2px;
  color: #1f2d3d;
}

.card-content-sender {
  font-size: 14px;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: -0.2px;
  color: #afb3b9;
}

.card-content-description {
  font-size: 16px;
  line-height: 24px;
  letter-spacing: -0.2px;
  color: #79818b;
  width: 100%;
  text-overflow: ellipsis;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
}
```


2. 

<img width="861" alt="same2" src="https://user-images.githubusercontent.com/75591730/167286446-487a4d8c-bce3-4240-b390-2a210243f861.png">

HTML 
```html 
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <title>Document</title>
  </head>
  <body>
    <ul class="tab-nav">
      <li class="tab-nav-item">
        <a href="#">Summary</a>
      </li>
      <li class="tab-nav-item active">
        <a href="#">Email</a>
      </li>
      <li class="tab-nav-item">
        <a href="#">Files</a>
      </li>
      <li class="tab-nav-item">
        <a href="#">Mentions</a>
      </li>
    </ul>
  </body>
</html>
```

CSS 
```css 
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Spoqa Han Sans", sans-serif;
  list-style: none;
}

html {
  font-size: 16px;
  font-family: "Spoqa Han Sans", sans-serif;
  letter-spacing: -0.03em;
  color: #212529;
}

body {
  padding: 100px;
  background-color: lightslategray;
}

.tab-nav {
  height: 52px;
  width: 540px;
  background-color: white;
  display: flex;
}

.tab-nav-item {
  height: 100%;
  display: flex;
  align-items: center;
}

.tab-nav-item a {
  padding: 0px 20px;
  font-weight: 400;
  color: #8492a6;
  text-decoration: none;
  font-size: 18px;
  line-height: 20px;
  letter-spacing: -0.2px;
}

.tab-nav-item.active {
  border-bottom: 2px solid #2860e1;
}

.tab-nav-item.active a {
  color: #2860e1;
  font-weight: 500;
}

```


3.

<img width="601" alt="same3" src="https://user-images.githubusercontent.com/75591730/167287938-13554b33-a951-4c48-b93b-a9d371639372.png">

HTML
```html 
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <title>Document</title>
  </head>
  <body>
    <section class="profile">
      <div class="profile-wrapper__top">
        <img src="./images/user.jpeg" alt="profile-image" />
        <h2 class="profile-name">Noah Madsen</h2>
        <span class="profile-location">Copenhagen, Denmark</span>
      </div>
      <ul class="detail-info">
        <li>
          <span class="detail-info indicator">Friends</span>
          <span class="detail-info number">730</span>
        </li>
        <li>
          <span class="detail-info indicator">Projects</span>
          <span class="detail-info number">3</span>
        </li>
        <li>
          <span class="detail-info indicator">Reviews</span>
          <span class="detail-info number">243</span>
        </li>
      </ul>
    </section>
  </body>
</html>

```

```CSS  
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Spoqa Han Sans", sans-serif;
  list-style: none;
}

html {
  font-size: 16px;
  font-family: "Spoqa Han Sans", sans-serif;
  letter-spacing: -0.03em;
  color: #212529;
}

body {
  background-color: lightslategray;
  padding: 100px;
}

.profile {
  background-color: white;
  height: 304px;
  width: 386px;
  border-radius: 16px;
  padding: 32px 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}

.profile img {
  height: 80px;
  display: block;
  margin: 0px auto;
  width: 80px;
  border-radius: 50%;
}

.profile-name {
  margin-top: 16px;
  font-weight: 600;
  font-size: 18px;
  line-height: 24px;
  text-align: center;
  color: #273444;
}

.profile-location {
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  color: #8492a6;
}

.detail-info {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.detail-info li {
  display: flex;
  flex-direction: column;
  text-align: center;
}

.detail-info.indicator {
  font-weight: 600px;
  font-size: 12px;
  line-height: 20px;
  display: block;
  margin-bottom: 4px;
}

.detail-info.number {
  font-weight: 300;
  font-size: 32px;
  line-height: 40px;
  display: block;
  color: #0066ff;
}

```






