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
