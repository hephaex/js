# JavaScript
- 브라우져에 실장된 스크립트 언어
- 동작이 있는 웹사이트를 만듬.
- JAVA와는 관계가 없음.
- 참조 사이트
  - [MDN](https://developer.mozilla.org/ko/docs/JavaScript)
- 필요한 지식 : HTML, CSS
- 사용 도구 : Google Chrome, 에디터

## Hello World
- JavaScript로 hello world를 출력해보자. 
- [js1.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js1.html)
- Browser Console에서 JS 실행 결과를 확인할수 있다. 
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
- <script> 태크를 사용하고 </script>로 닫는다.
- 외부에서 읽어 올때는 <script src="myscript.js"> </script>를 사용한다.
- 크롬에서 브라우저 보기->개발자도구->자바스크립트를 활성화해서 콘솔은 띄운다.
- 파이어폭스에서는 tool->Web Developer->Browser Console 로 콘솔을 띄운다.

- 외부 스크립트를 읽어서 실행해보자.
- 외부 스크립트는 myscript.js로 했다. 
- [js2.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js2.html)
```myscript.js
console.log("hello from script");
```

## 변수와 함수를 사용해 보자.
- 변수: 데이터를 담고 있는 공간
- var msg;  // msg변수 선언.
- msg = "hello world!"; // 변수 대입
- console.log(msg); // 변수 출력
- [js3.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js3.html)
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
- var 으로 변수를 선언한다.
- ex)
```
var msg = "hello world!",
x = 20,
y = 10;
- [js4.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js4.html)
```
- 데이터 형
  - 문자열
  - 수식 (10 , - 2.5, -2.5)
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
- [js5.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js5.html)
```
    var x;
    x = 10 * 2; //20
    x = 10 % 3; // 1
    x = x + 5;  // 6
    x += 5;     // 10
    x ++ ;      // 11
    x -- ;      // 10
```

### 문자열
- 표현 방식
- 특수 문자
- 연산자
- [js6.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js6.html)
```
    var s;
    s = "hello";
    s = 'hel\'lo';
    // \n 개행
    // \t 탭
    s = 'it\'s\n a pe\tn.'; //it's   a pe   n

    s = "hello " + "wolrd"; //"hello world"

    s = "5" + 5;   // "55" 문자로 결합된다는 것에 주의
    console.log(s);
```
```
"hello"       js6.html:11
"hello"       js6.html:13
"hel'lo"      js6.html:17
"it's
n."           js6.html:19
"hello wolrd" js6.html:21
"55"          js6.html:23
```

## if문
- 비교 연산자
  -  > <
  -  >= <=
  -  === ==
  -  !== !=
- 논리 연산자
  - AND &&
  - OR  ||
  - NOT !
  - ex) score > 60 && score < 80 
- 조건 분기
  - 사용법
  if (조건) {
    참
  } else {
    부정 
  }
- [js7.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js7.html)
```
    var score = 80;
    if (score > 60) {
    console.log("ok!");
    } else {
    console.log("fail!");
    }
```

## 진위문과 삼항연산자
- 문자열이외라면 true
- 수치가 0가 NaN이외라면 true
- true / false
- object : null 이외라면 true
- undefined, null -> false
- if (x) {
   // 처리
  }
- if (x != '') {
  // 처리 
  }
- 삼항연산자. 
```
var a, b, c;
if (조건) {
a = b;
} else {
a = c;
}
```
```
a = (조건) ? b: c;
```

```
var max, x, y;
max = (x > y) ? x : y;
```
- [js8.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js8.html)

## switch 문을 사용해 보자.
- switch
- [js9.html](https://github.com/hephaex/js/blob/master/04_JavaScript/js9.html) 
```
  var signal = "blue" ;
  switch (signal) {
      case "red":
      console.log("stop!");
      break;
      case "green":
      case "blue":
      console.log("Go !");
      break;
      case "yellow":
      console.log("slow down !");
      break;
      default :
      console.log("wrong signal !");
      break;
    }
```
