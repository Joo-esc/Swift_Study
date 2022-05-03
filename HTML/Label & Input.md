## Label, Input
## 개념
- 사용자한테 정보를 받기 위한 가장 기본적인 태그
- 타입 속성을 꼭 명시해야됨
  - ex) `<input type="text"  />`
- type을 지정해 유효성 검사를 고려할 수 있음

2. Label
- 폼 양식에 이름을 붙이는 태그
- 선언시 아래와 같은 신택스를 준수해야됨
```html
<label for ="인풋id">라벨</label>
<input id ="인풋id" type="text"/>
```
- label과 input id를 맵핑 시 focouse Effect가 발동됨 (사용자 경험 고려)

## 코드
```html
<!DOCTYPE html>
<html lang="kr">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <title>Emphasis</title>
  </head>
  <body>
    <form action="">
      <input
        type="text"
        placeholder="아이디 입력 필요"
        minlength="5"
        maxlength="13"
        required
        value="초기 값"
      />
      <input
        type="text"
        placeholder="비밀번호 입력"
        minlength="5"
        maxlength="13"
        required
      />
      <button>Submit</button>
    </form>
  </body>
</html>

```

## 구현물
<img width="544" alt="input1" src="https://user-images.githubusercontent.com/75591730/166407478-223ec4b6-4ae0-4237-b255-b54d7be86e4e.png">
