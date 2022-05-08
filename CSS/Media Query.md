# Media Query 
- `반응형 웹` 을 구축하기 위해 필요한 CSS 선언 중
- Media Query를 이용하기위해서는 아래와 같이 viewport가 설정이 되어야 함.
  - html : viewport meta
    ```html
    <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    </head>   
    ```
  - 웹 페이지의 가로 사이즈 == 사용자 디바이스의 가로 사이즈를 기준으로 함 
- css : meida query
  - ```css
     @media screen and (min-width: 768px) {
        .. some intent here..
    }
    ```
  - 특정 `break point` 사이즈를 기준으로 특정 스타일 변화를 필요할 때 사용
  
## 동작 조건
`screenWidth >= 768`<br>
스크린 넓이가 최소 768px 이상일 때 
```css  
    @media screen and (min-width: 768px) {
    // 변화가 필요한 값들 선언 
        .box {
            background-color : someColor
        }
    }
```

`991 >= screenWidth >= 768`<br>
스크린 넓이가 최소 768px 이상 991px 이하 일 때
```css  
    @media screen and (min-width: 768px) and (max-width: 991) {
        .box {
            background-color : someColor
        }
    }
```

min-width 최소 가로 길이가 이상일 때  
``` ```


## 예제 실습
<img src="https://user-images.githubusercontent.com/75591730/167298300-c19f9580-7c78-4980-a25f-3e3a76a376c3.gif">
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
    <div class="bg-image">
      <aside class="banner"><a href="#">🚗 8월 게스트 신청하기</a></aside>
      <div class="landing-content">
        <h1>
          <strong>Eat, pray, work</strong> <br />
          심야의<br />
          디지털노마드 민박 <br />
          #치앙마이 <br />
          #8월예약오픈
        </h1>
        <a href="#">둘러보기</a>
      </div>
    </div>
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
    text-decoration: none;
}

html {
    font-size: 16px;
    font-family: "Spoqa Han Sans", sans-serif;
    letter-spacing: -0.03em;
    color: #212529;
}

a {
    color: inherit;
}

body {
    background-color: lightslategray;
}

.bg-image {
    height: 100vh;
    width: 100vw;
    background: url("./images/img-bg.jpg") no-repeat center;
    background-size: cover;
}

.banner {
    background-color: #ffc82c;
    height: 80px;
    width: 100%;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    line-height: 24px;
    letter-spacing: -0.01em;
    color: #1f2d3d;
    font-weight: 700;
}

.landing-content {
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: center;
    align-items: center;
}

.landing-content h1 {
    color: white;
    font-weight: 700;
    font-size: 50px;
    text-align: center;
}

.landing-content a {
    height: 56px;
    width: 180px;
    border: 2px solid #ffff;
    background: rgb(0, 0, 0, 0.5);
    border-radius: 16px;
    display: block;
    color: #ffff;
    font-weight: 700;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 18px;
    line-height: 24px;
    letter-spacing: -0.01em;
    margin-top: 32px;
}

/* Mobile Size  */
@media screen and (max-width: 667px) {
    .pop-up {
        height: 64px;
        bottom: 0;
    }

    .landing-content {
        align-items: flex-end;
        margin-right: 20px;
    }

    .landing-content h1 {
        font-size: 32px;
        text-align: end;
    }

    .landing-content button {
        height: 52px;
        width: 160px;
        font-size: 14px;
    }
}

```