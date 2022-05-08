# Naming Conventions in HTML

> 본 포스팅에서는 편의상 화면에 보여지는 요소를 `UI`로 명칭을 통일합니다  


Flutter 와 Swift를 사용하여 모바일 앱 개발을 하다가, 최근에 웹 공부를 시작하면서 가장 어색했던 부분은 HTML & CSS의 `스타일링` & `레이아웃` 로직이었다.<br>

<img width="200" src="https://user-images.githubusercontent.com/75591730/167249690-40ac35d8-8d4c-4663-b506-19f1277c29b5.png">
<img width="200" src="https://user-images.githubusercontent.com/75591730/167250042-69272654-8b99-4c2d-9b67-8ffbc717468a.png">

위에 그림에서 확인할 수 있듯이 `HTML + CSS`는 화면에 보여지는 UI의 `뼈대`와 UI를 꾸미는 `스타일`을 분리하여 화면을 구성하는 코드로 이루어져 있지만, 

Flutter의 경우 하나의 UI 코드에 `뼈대`와 `스타일링`로직 결합되어 있는 형태이다.
둘 다 `선언형 프로그래밍` 방식이라는 공통점이 있지만 렌더링 방식에 따라 다른 접근 방식을 채택하고 있다.


>_혹시 CSS와 Widget(Flutter)의 차이점을 자세하게 확인해보고 싶다면 해당 <a href="https://www.alibabacloud.com/blog/breakdown-a-detailed-comparison-between-the-flutter-widget-and-css-in-terms-of-layout-principles_596987">블로그 포스팅<a/>을 참고해도 좋을듯 하다._ <br>

**여기서 문제점이 발생는데..** 웹에서는 주로 HTML의 `id` 또는 `class`(대부분 class)를 활용하여 CSS에서 스타일링 규칙을 적용할 요소를 정의하기 때문에 `변수명`을 적는 경우가 상대적으로 너무 많고,

프로젝트 규모가 커질수록 HTML 요소의 `id` & `class` 변수명을 짓기 굉장히 까다로워진다.ㅁ 

그럼 과연 `프로`들은 어떻게 변수명을 지을지가 궁금해졌고 좋은 `class name`이 무엇일지에 대해 물음표가 생겼다. 


## CSS만 보고도 알 수 있어야된다.
포스팅과 유튜브를 통해 리서치 해본 결과 각자 제시하는 변수명을 적는 방법의 디테일들은 조금씩 다르지만, 공통적으로 `시멘틱한(semantic)한 변수명`을 강조했다.  












