두 가지의 데이터 타입

자바스크립트는 크게 두가지 타입으로 분류됨
1. Primitive Type (기본형)
   1. Number
   2. String
   3. Boolean
   4. null
   5. undefined
   6. Symbols(es6)
2. Reference (참조형)
   1. object
      1. Array
      2. Function
      3. RegExp
      4. Set / WeakSet (es6)
      5. Map / WeakMap

둘을 구분하는 이유와 차이를 각 데이터가 메모리상에서 저장되는 관점에서 확인 해보려고 한 

메모리 동작 관리 

자바스크립트 메모리 구조 
- stack memory
  - 변수
  - 기본형 데이터
  - 정적 할당
 
- heap memory
  - 참조형 데이터
  - 동적 할당