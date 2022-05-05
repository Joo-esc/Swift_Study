## 코드
```html
<!DOCTYPE html>
<html lang="kr">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />

    <title>Count App</title>
  </head>
  <body>
    <form>
      <label for="programming language">Language</label>
      <select multiple name="programming language">
        <option value="0">Swift</option>
        <option value="1">Kotlin</option>
        <option value="2">Javascript</option>
      </select>
      <button type="submit">submit</button>
    </form>
    <form>
      <label for="programming language">Language</label>
      <select name="programming language">
        <option value="0">Swift</option>
        <option value="1">Kotlin</option>
        <option value="2">Javascript</option>
      </select>
      <button type="submit">submit</button>
    </form>
  </body>
  <script src="main.js"></script>
</html>
```

## 구현물
<img width="300" alt="select" src="https://user-images.githubusercontent.com/75591730/166638715-b03a25b2-9e33-4fea-92c1-1208d9a825a7.png">