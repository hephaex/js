# JavaScript
- 브라우져에 실장된 스크립트 언어
- 동작이 있는 웹사이트를 만듬.
- JAVA와는 관계가 없음.
- 참조 사이트
  - [MDN](https://developer.mozilla.org/ko/docs/JavaScript)
- 필요한 지식 : HTML, CSS
- 사용 도구 : Google Chrome, 에디터

## 기본
```
<!DOCUTYPE html>
<html lang="ko">
<head>
 <meta charset="utf-8">
 <title>JavaScript 연습</title>
</head>
<body>
  <script src="myscript.js"></script>
  <script>
    console.log("Hello World!");
  </script>  
</body>
</html>
```
- [js1.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js1.html)

- <script> 태크를 사용하여 일고, </script>로 닫는다.
- 외부에서 읽어 올때는 <script src="myscript.js"> </script>를 사용한다.
- 크롬에서 브라우저 보기->개발자도구->자바스크립트를 활성화 해서 콘솔은 띄운다.

```myscript.js
console.log("hello from script");
```

## 변수를 사용해 보자.
```
<!DOCUTYPE html>
<html lang="ko">
<head>
 <meta charset="utf-8">
 <title>JavaScript 연습</title>
</head>
<body>
  <script>
    var msg;
    msg = "hello World";
    console.log(msg);
  </script>  
</body>
</html>
```
- [js3.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js3.html)

## 변수를 사용해 보자.
- var 으로 변수를 선언한다.
- ex)
```
var msg = "hello world!",
x = 20,
y = 10;
```
- 데이터 형
  - 문자열
  - 수식
    - 10
    - 2.5
    - -2.5
  - 연산식 
    - + - * / %
    - += 대입 연삭식
    - ++ -- 단순 연산식
  - 진리식 (true/false)
  - 오브젝트
    - 배열
    - 함수
    - 내장형 오브젝트
  - undefined 정의되지 않는다.
  - null 아무것도 아니다. 
```
    var x;
    x = 10 * 2; //20
    x = 10 % 3; // 1
    x = x + 5;  // 6
    x += 5;     // 10
    x ++ ;      // 11
    x -- ;      // 10
```
- [js4.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js4.html)

