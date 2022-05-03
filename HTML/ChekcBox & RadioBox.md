## CheckBox RadioButton
## 개념
RadioButton & Check Box
- id, name, value 속성 정의 필요
  - toggle effect, data 처리 등을 위해 정의가 필요
- 복수, 단일 선택에 따라 각각에 맞는 태그를 이용하면 됨
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
    <!-- Radio Button Example -->
    <form>
      <label for="subscribe"> 구독 중 </label>
      <input id="subscribe" name="subscription" type="radio" value="sub" />
      <label for="unsubscribe"> 구독 중 </label>
      <input id="unsubscribe" name="subscription" type="radio" value="unsub" />
      <button type="submit">제출</button>
    </form>
    <!-- Check Box Example -->
    <form>
      <input type="checkbox" name="html" />
      <label for="html">HTML</label>
      <input type="checkbox" name="css" />
      <label for="css">CSS</label>
      <input type="checkbox" name="js" />
      <label for="js">JS</label>
      <button type="submit">제출</button>
    </form>
  </body>
</html>

```


##구현물
<img width="544" alt="input1" src="https://user-images.githubusercontent.com/75591730/166409562-13f6a507-b507-4411-91b3-858f0fd2a212.png">

