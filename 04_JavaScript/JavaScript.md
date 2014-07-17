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

### 문자열
- 표현 방식
- 특수 문자
- 연산자

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

## if문
- 비교 연산자
  -  > <
  -  >= <=
  -  === ==
  -  !== !=
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
  - ex)

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
- var a, b, c;
  if (조건) {
   a = b;
  } else {
   a = c 
  }
  a = (조건) ? b: c;
- var max, x, y;
  max = (x > y) ? x : y;

## switch 문을 사용해 보자.
- switch
 
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
  
## 루프 처리
- while, do ... while
/*
  루프 처리
  while
  do ... while
  for
  break    : 루프 처리 중단
  continue : 루프 처리 진행
*/

```
var i = 0;
while (i < 10) {
  console.log(i);
  i++;
}
```

```
var i = 0;
do {
    console.log(i);
    i++;
} while (i < 10);
```

```
for (var i = 0; i < 10; i++) {
  if ( i == 5) { break; }
  console.log(i);
}
```

## 알림 표시
- alert : 알림 메시지 박스 표시
  - alert("hello");
- confirm :
  - var answer = confirm("are you sure?");
    console.log(answer);
- promt :
  - var name = prompt("Input your name?", "name" );
    console.log(name);

## 함수
- 복수의 처리를 하는 묶음.
- function 함수명(매개변수) {
   처리 
   return 반환값
  }

```
function hello(name){
 return ("hello" + name);
}
var great = hello("foo");
console.log(great);
```

- 지역함수를 사용해 보자.

```
function hello1(name) {
  var msg = "hello " + name; 
  return msg;
}
var hello2 = function (name) {
  var msg = "hello " + name; 
  return msg;
};
var greet = hello1("tom");
console.log(great);
console.log(hello2="bar");
console.log(msg);
```

- 즉시함수를 사용해 보자.
``` 
(function hello(name){
 console.log("hello" + name);
})("foo");
(function (name){
 console.log("hello" + name);
})("bar");
(function (){
 var x = 10,
     y = 20;
 console.log(x + y);
})();
```

## timer 처리
- seInterval : 일정시간 동안 반복, 앞에 처리에 상관 없이실행
- setTimeout : 일정시간에 한번만 실행, 앞의 처리이후 실행
```
var i = 0;
    function show(){
    console.log(i++);
    }
    setInterval(function() {
    show();
    }, 1000);
    setTimeout(function() {
    show();
    }, 1000);
    show();
```

```
var i = 0;
function show(){
 console.log(i++);
 setTimeout(function() {
 show();
 }, 1000);
}
 show();
```

```
    var i = 0;
    function show(){
    console.log(i++);
    var tid setTimeout(function() {
    show();
    }, 1000);
    if (i > 3) {
     clearTimeout(tid);
    }
    show();
```

## 배열을 사용해 보자.
- var score_1 = 100, score_2 = 200;

```
var score = [100, 300, 500, "name"];
console.log(score[0]);
score [2] = 400;
console.log(score);

var m = [  
  [ 1, 2, 3],
  [ 4, 5, 6]
 ];
console.log(m[1][1]);
``` 

## 오브젝트를 사용해 보자.
- 배열처럼 그룹화된 데이터 (이름과 값)

```
var user = {
 email : "hephaex@gmail.com", //프로퍼디
 score : 80
};

console.log(user["email"]);
console.log(user.email);
console.log(user.score);
user.score = 100;
console.log(user.score);
```

## 메소드를 사용해 보자.
- 프로퍼티에 함수를 사용할수도 있다. 
- 메쏘드는 자신의 오브젝트를 가리키는 this를 사용 다른 프로퍼티를 참조할수 있다. 
 - great 에서 this.email 참조
```
var user = {
 email : "hephaex@gmail.com", //프로퍼디
 score : 80
 great : function(name) { // 메소드
  console.log("hello" + name + "from " + this.email );
 }
};

console.log(user["email"]);
console.log(user.email);
console.log(user.score);
user.score = 100;
console.log(user.score);
console.great("foo");
```

## 내장형 오브젝트
- String
- Array
- Math
- Date

```
// var s = "hephaex";  // 문자열 리테럴
var s = new String("hephaex"); //문자열 오프젝트

console.log(s.length); // 8
console.log(s.replace("t","T")); //대문자로
console.log(s.substr(1,3));
```

```
var a = new Array(100,300,200);
// var a = [100,300,200];

console.log(a.length); // 3
// unshift -> array <- push
// shift <- array -> pop
a.push(500);
console.log(a); // 100 300 200 500
a.splice(1,2); // 300 200 삭제
console.log(a); // 100 500
a.splice(1,2, 800,1000);  
console.log(a); // 100 800 1000 
```

- new를 사용하지 않고 바로 사용

```
console.log(Math.PI);
console.log(Math.ceil(5.3)); // 반올림
console.log(Math.floor(5.3)); // 내림
console.log(Math.round(5.3)); // 올림
console.log(Math.random());   // 임의의 수
```

- 월은 0월부터 시작하므로 2월은 1이다. 
```

var d = new Data();
// vad d = new Data(2014, 1, 11, 10, 20, 30);
var d1 = new Data(2014, 1, 11, 10, 20,30);
console.log(d.getFullYear()); //년을 표시
console.log(d.getMonth());  //월을 표시
console.log(d.getTime()); // 1970년 1월 1일부터 경과한 mSec
console.log(d1.getFullyYear());
console.log(d1.getMonth());
console.log(d1.getTime());
```

## DOM

```
console.dir(window);
console.log(window.outerHeight); // 사용자 윈도 크기를 구함
// window.location.href = 'http://manseok.blogspot.com';
// window.document // 지금 보고 있는 페이지
// document 만으로도 사용가능
// document object model (DOM)
```

```
<!DOCUTYPE html>
<html lang="ko">
<head>
 <meta charset="utf-8">
 <title>JavaScript 연습</title>
 <style>
  .myStyle {
   font-weigh : bold;
   border: 1px solid gray;
  }
 </style>
</head>
<body>
  <h1> example 보기 </h1>
  <p id="msg"> 안녕하세요 </p>
  <script>
    var e = document.getElementById('msg');
    e.textContect = "hello";
    e.style.colr = 'red';
    e.className = 'myStyle';

    /*  
      body
          p 
            text
    */
    var great = document.createElement('p'),
        text  = document.createTextNode('hello world');
    document.body.appendChild(great).appendChild(text);
 </script>
</body>
</html>
```

## 이벤트를 설정해보자.
```
<!DOCUTYPE html>
<html lang="ko">
<head>
 <meta charset="utf-8">
 <title>JavaScript 연습</title>
</head>
<body>
  <h1> example 보기 </h1>
  <p id="msg"> 안녕하세요 </p>
  <button id="add"> Click ! </button>
  <script>
   var e = document.getElementById('msg');
   e.textContent = 'hello! ';
   e.style.color = 'red';
   e.className = 'myStyle';


   document.getElementById('add').addEventListener('click', function(){
    var great = document.createElement('p'),
       text  = document.createTextNode('hello world');
   document.body.appendChild(great).appendChild(text);
   });
  </script>  
</body>
</html>
```
