# css
- Cascading sytle Sheet
- HTML 문서구조 + CSS(형식) = web페이지
- CSS 3

## 기본구성
[css1-1.html](https://github.com/hephaex/js/blob/master/02_css/css1-1.html)
```css.html
<!DOCYTYPE html>
<html lang="ko">
<head>
  <meta charset="utf-8"
  <title>CSS example</title>
  <style>
    h1 {color:red;}
    </style>
  <link rel="stylesheet" href="default.css"> <!-- outer style -->
</head>
<body>
  <section id="main">
    <h1> 예시 </h1>
    <p class="item"> 안녕하세요. </p>
  </secion>
  <section id="sub">
    <h2> 예시 </h>
    <p style="color: green;"> 안녕하세요 </p> <!-- inline style -->
    <ul>
      <li> item 1 </li>
      <li class="item"> item 2 </li>
      <li> item 3 </li>
  </secion>
</body>
</html>
```

### css의 기본 구성
```
셀렉터 {
 프로퍼티 : 값;
 프로퍼티 : 값; 
 프로퍼티 : 값;
}
```

예시)
```
h1 {
    /* 코멘트 */
    color: red;
}
```

#### css를 지정하는 것들
- html 요소
  - h1
  - p
  - u1
- id를
  - "#main"
  - "#sub"
- class
  - .item

## css를 어디에 쓸까.
### style 태크
[css3-1.html](https://github.com/hephaex/js/blob/master/02_css/css3-1.html)
```css3-1.html
<head>
  <title>CSS example</title>
  <style>
    h1 { color: red;}
  </sytle>
</head>
```

### 인라인
[css3-2.html](https://github.com/hephaex/js/blob/master/02_css/css3-2.html)
```ocss3-2.html
<p style="color: green;"> 안녕하세요 </p>
```

- 외부 파일
default.css를 링크를 걸어서 사용한다.
<head> ... </head>안에 넣어서 사용한다. 
<link rel="sytlesheet" href="default.css">
[css3-3.html](https://github.com/hephaex/js/blob/master/02_css/css3-3.html)
```css3-3.html
<head>
  <title>CSS example</title>
  <link rel="stylesheet" href="default.css">
</head>
```

```default.css
ul {
    color: pink;
}
```

## select 를 사용해 보자.

#### *
- [css4-1.html](https://github.com/hephaex/js/blob/master/02_css/css4-1.html)
- 모든 셀렉터를 의미
- 모든 것을 빨강색으로 만듬.
>  '*'' { color: red;}

#### a, b
- [css4-2.html](https://github.com/hephaex/js/blob/master/02_css/css4-2.html)
- 복수를 셀렉터를 설정할수 있다. 
- h1 과 h2를 모두 빨강색으로 만듬.
> h1, h2 {color: red;}

#### a b
- [css4-3.html](https://github.com/hephaex/js/blob/master/02_css/css4-3.html)
- 섹션의 바로 아래 아이템만 설정
> section .item {color: red;}

#### a > b
- [css4-4.html](https://github.com/hephaex/js/blob/master/02_css/css4-4.html)
- a섹션의 바로뒤 b요소를 설정
> section > .item {color:red;}

#### a + b
- [css4-5.html](https://github.com/hephaex/js/blob/master/02_css/css4-5.html)
- a섹션의 바로뒤 b요소를 설정
- select id="main" 에서 가장 가까운 item만을 빨강색으로 만듬.
> h2 + p {color:red;}

#### a * b
- [css4-6.html](https://github.com/hephaex/js/blob/master/02_css/css4-6.html)
- p요소중에 b구성요소를 설정
  - p item으로 지정한 것만 빨강색으로 만듬.
> p.item { color: red;}

## 스타일 지정 우선 순위
1. 셀렉터가 동일하다면 나중의 것이 우선된다.
  - 녹색으로 출력된다.
  - [css5-1.html](https://github.com/hephaex/js/blob/master/02_css/css5-1.html)
```
h1 {color: red;}
h1 {color: green;}
```

2. 아웃보다는 인라인이 우선된다.
  - 앞에서 스타일로 녹색을 정의했지만,
  - 인라인으로 설정한 핑크가 출력된다.
  - [css5-2.html](https://github.com/hephaex/js/blob/master/02_css/css5-2.html)
```
<style>
 h1 {color:green;}
</style>

...
<h1 style="color:pink"> main 예시 </h1>
```

3. 요소가 높은 것이 우선된다.
  - # 라벨은 100의 우선순위
  - . 은 10의 우선순위
  - 요소는 1의 우선순위
  - [css5-3.html](https://github.com/hephaex/js/blob/master/02_css/css5-3.html)
  - 예시로 우선순위를 계산해 보면
  - section#main 이 1 + 100 + 1로 우선된다.
```
h1{color:green;} /* 1 */
#main h1 {color:red} /* 100 +1 */
section#main h1 {color: yellow;} /* 1 + 100 + 1 */
```

4. !important 가 최우선된다.
  - !important 가 붙으면 우선순위가 낮더라도 최우선된다.
  - [css5-4.html](https://github.com/hephaex/js/blob/master/02_css/css5-4.html)
```
h1 {color:red !important;}
#main h1 {color:green;}
section#main h1 {color: yellow;}
```

## 색을 지정해 보자.
- 이름으로 지정
  - red blue purple
```
h1 {color: blue;}
```
- RGB로 지정
  - r(ed)/g(reen)/b(lue) 0~255
  - rgb(0,255,0)
  - [css6-1.html](https://github.com/hephaex/js/blob/master/02_css/css6-1.html)
```
h1 {color: rgb(0,255,0);}
```	
- 16진수로 지정
  - '#00f /* blue */
  - '#ff0000 /* red */
  - [css6-2.html](https://github.com/hephaex/js/blob/master/02_css/css6-2.html)
```
h1 {color: #ff0000;}
```

## 텍스트 스타일을 지정
- 색상 [css7-1.html](https://github.com/hephaex/js/blob/master/02_css/css7-1.html)
 - color : gray;
- 문자 속성 [css7-2.html](https://github.com/hephaex/js/blob/master/02_css/css7-2.html)
 - font-weight: bold;
 - font-weight: normal;
- 문자 크기 [css7-3.html](https://github.com/hephaex/js/blob/master/02_css/css7-3.html)
 - font-size : 14px
 - font-size : 20px
 - font-size : 32px
- 문단 정렬 [css7-4.html](https://github.com/hephaex/js/blob/master/02_css/css7-4.html)
 - text-align: center;
 - text-align: left;
 - text-align: right;
- 문단 꾸미기 [css7-5.html](https://github.com/hephaex/js/blob/master/02_css/css7-5.html)
 - text-decoration: line-through;
- 글꼴 지정 [css7-6.hyml](https://github.com/hephaex/js/blob/master/02_css/css7-6.html) 
 - font-family: Impact;
- 간격 조정 [css7-7.html](https://github.com/hephaex/js/blob/master/02_css/css7-7.html)
 - line-height: 40px;

## 배경을 지정해 보자
- 배경을 녹색으로 지정해 보자
  - background-color: green;
  - [css8-1.html](https://github.com/hephaex/js/blob/master/02_css/css8-1.html)
- 배경에 이미지를 넣어보자. 
  - background-repeat: no-repeat;
  - [css8-2.html](https://github.com/hephaex/js/blob/master/02_css/css8-2.html)
- 배경을 반복을 하지 않게 조정해 보자.
  - background-repeat: no-repeat;
  - [css8-3.html](https://github.com/hephaex/js/blob/master/02_css/css8-3.html)  
- 배경을 반복을 X축으로 조정해 보자.
  - background-repeat: repeat-x;
  - [css8-4.html](https://github.com/hephaex/js/blob/master/02_css/css8-4.html)  
- 배경을 반복을 Y축으로 조정해 보자.
  - background-repeat: repeat-y;
  - [css8-5.html](https://github.com/hephaex/js/blob/master/02_css/css8-5.html)  
- 배경의 위치를 설정해보자.
  - background-position: 10px 10px;
  - [css8-6.html](https://github.com/hephaex/js/blob/master/02_css/css8-6.html)
- 스크롤되었을 때 배경그림이 함께 스크롤하도록 해보자.
  - background-attachment: scroll;
  - [css8-7.html](https://github.com/hephaex/js/blob/master/02_css/css8-7.html)
- 스크롤되었을 때 배경그림이 함께 스크롤하도록 해보자.
  - background-attachment: fixed;
  - [css8-8.html](https://github.com/hephaex/js/blob/master/02_css/css8-8.html)
- 배경을 한번에 지정해보자.
  - background: green url('bg.png') no-repeat;
  - [css8-9.html](https://github.com/hephaex/js/blob/master/02_css/css8-9.html)

## 박스를 그려보자.
- 바탕이 녹색이고, 가로 400px, 세로 400px를 그려보자.
```
div {
  background: green;
  width: 400px;
  height: 400px;
}
```
  - [css9-1.html](https://github.com/hephaex/js/blob/master/02_css/css9-1.html)
- 바탕이 녹색이고, 가로비가 50%, 세로비가 50%를 그려보자.
```
div {
  background: green;
  width: 50%;
  height: 50%;
}
```
  - [css9-2.html](https://github.com/hephaex/js/blob/master/02_css/css9-2.html)
- 브라우저에 따라서 높이를 지정할 경우가 있다. 
```
body,html {
  height:100%;
}
div {
  background: green;
  width: 50%;
  height: 50%;
}
```
  - [css9-3.html](https://github.com/hephaex/js/blob/master/02_css/css9-3.html)

## border를 사용해 보자.
- 테두리 색깔
  - border-color
- 테두리 크기
  - border-width
- 테두리 속성
  - border-style solid dashed dotted double inset outset
- 테두리 색깔, 크기, 속성을 한번에 지정해보자. 
  - border red 5px solid;
  - [css10-1.html](https://github.com/hephaex/js/blob/master/02_css/css10-1.html)
- 테두리가 점선으로 지정해보자. 
  - border red 5px dashed;
  - [css10-2.html](https://github.com/hephaex/js/blob/master/02_css/css10-2.html)
- 테두리가 안쪽으로 속성을 지정해보자.
  - border red 5px inset;
  - [css10-3.html](https://github.com/hephaex/js/blob/master/02_css/css10-3.html)
- 테두리가 바깥쪽으로 속성을 지정해보자.
  - border red 5px outset;
  - [css10-4.html](https://github.com/hephaex/js/blob/master/02_css/css10-4.html)
- 테두리가 왼쪽과 오른쪽의 속성을 지정해보자.
  - border red 5px outset;
  - [css10-5.html](https://github.com/hephaex/js/blob/master/02_css/css10-5.html)
  
## padding, margin
- 브라우져가 자동으로 간격을 떨어뜨리므로
- margin: 0; 으로 설정하자.
```
body,html {
        height:100%;
        margin: 0;
      }
```
- 등간격으로 띄워보자.
 -  padding: 10px;
 - [css11-1.html](https://github.com/hephaex/js/blob/master/02_css/css11-1.html)
- 좌/우/상/하 간격을 띄워보자.
 - 1 -> all
 - 2 -> top&bottom left&right
 - 3 -> top left&right bottom
 - 4 -> top right bottom left
 - padding: 10px 20px 30px 40px;
 - [css11-2.html](https://github.com/hephaex/js/blob/master/02_css/css11-2.html)
- 한쪽만 간격을 조정해 보자.
 - padding-left : 10px;
 - marging : 20px;
 - [css11-3.html](https://github.com/hephaex/js/blob/master/02_css/css11-3.html)
 - padding-left : 10px;
 - marging-left : 20px;
 - [css11-4.html](https://github.com/hephaex/js/blob/master/02_css/css11-4.html)

## display overflow
- 요소의 표시방법을 지정하는 display
- display
  - block       // 전후에 개행이 들어감
  - inline      // 전후에 개행이 들어가지 않음.
  - inline-block // 전후에 개행이 들어가지 않음.
  - none
  - 스크립트로 해서 자주 사용함.
- 기본적으로 블록으로 정의되므로
  - <div> box </div> <div> box </div> <div> box </div>이면
  - 세로로 나열된다. 
  - [css12-1.html](https://github.com/hephaex/js/blob/master/02_css/css12-1.html)
- 이것을 가로로 바꾸면. inline을 사용한다.
  - display: inline;
  - [css12-2.html](https://github.com/hephaex/js/blob/master/02_css/css12-2.html)
- 가로에 세로의 폭을 블록으로 지정할때는 inline-block을 사용한다.
  - [css12-3.html](https://github.com/hephaex/js/blob/master/02_css/css12-3.html)
- 표시하고 싶지 않을 때는 none을 사용한다.
  - [css12-4.html](https://github.com/hephaex/js/blob/master/02_css/css12-4.html)
- overflow
 - 요소 안에서 표시 영역을 지정하는 overflow
 - 영역을 넘어갈 때
   - [css12-5.html](https://github.com/hephaex/js/blob/master/02_css/css12-5.html)
 - 영역을 넘어갈 때 넘어간 부분을 숨길 때 overfloe: hidden;을 사용한다.
   - [css12-6.html](https://github.com/hephaex/js/blob/master/02_css/css12-6.html) 
 - 영역을 넘어갈 때 넘어간 부분을 스크롤로 보여줄 때 overfloe: scroll;을 사용한다.
   - [css12-7.html](https://github.com/hephaex/js/blob/master/02_css/css12-7.html) 

## position
- 요소의 배치 방법을 지정함
 - static: 고정시킬 때
 - relative : 부모요소
 - absolute : 자식요소
 - fixed
- new라는 lable을 만들어 요소 배치를 지정해 보자.
  - [css13-1.html](https://github.com/hephaex/js/blob/master/02_css/css13-1.html)
- div는 position relative로 지정하고, label은 absolute로 지정
  - [css13-2.html](https://github.com/hephaex/js/blob/master/02_css/css13-2.html)
- 'hi'를 오른쪽 아래에 조금 어긋나게 표현해 보자.
  - [css13-3.html](https://github.com/hephaex/js/blob/master/02_css/css13-3.html)

## z-index
- 스크롤을 하여도 위치가 바뀌지 않게 만들어 보자.
  - div#menu를 만들자.
  - <div id="menu"> Menu </div>
  - 스타일에서 div#menu속성을 정의하자.
  - 여기서는 fixed를 사용해 보자.
``` 
      div#menu {
        position: fixed;
        bottom: 0;
        background: blue;
        color: white;
        width: 100%;
        height: 50px;
      }
```
  - 스크롤을 해도 div#menu는 고정된다.
  - [css14-1.html](https://github.com/hephaex/js/blob/master/02_css/css14-1.html)
- menu를 아래에서 위로 옴길 수도 있다.
  - bottom: 0; --> top: 0;으로 바꾼다.
  - [css14-2.html](https://github.com/hephaex/js/blob/master/02_css/css14-2.html)
- z-index
  - static 이외 표시 순서를 표현함
  - 크기가 클 수록 윗쪽에 표시
  - div는 z-index: 1;
  - div#menu는 z-index: 2;
  - div#menu가 div보다 z-index가 크므로 div#menu가 위에 표시된다.
  - [css14-3.html](https://github.com/hephaex/js/blob/master/02_css/css14-3.html)

## float, clear
- float : 그림 옆에 문자가 오게 만듬
```
img {
  float : left;
  }
```
  - [css15-1.html](https://github.com/hephaex/js/blob/master/02_css/css15-1.html)
 - clear : 그림 옆에 문자가 오지 않게 만듬.
```
h2 {
      clear: left;
       /* left right both */
      }
```
  - [css15-2.html](https://github.com/hephaex/js/blob/master/02_css/css15-2.html)

## list-style
- list-style-type  마커의 종류
  - list-style-type: circle;
  - list-style-type: square;
  - list-style-type: number;
  - [css16-1.html](https://github.com/hephaex/js/blob/master/02_css/css16-1.html)
- list-style-position 마커의 위치
  - list-sytle-position: outside;
  - list-style-position: inside;
  - [css16-2.html](https://github.com/hephaex/js/blob/master/02_css/css16-2.html)
- list-style-image 마커를 그림으로 표시
  - list-style: url('xxx.xxx') outside;
```
<style>
 ul {
  list-style : url('bg.png') outside;
  }
</style>
```
 - [css16-3.html](https://github.com/hephaex/js/blob/master/02_css/css16-3.html)

## cursor
- 해당 스타일에 들어가면 cursor 모양을 바꿈.
 - cursor : move
 - move
  - [css17-1.html](https://github.com/hephaex/js/blob/master/02_css/css17-1.html)
 - help
  - [css17-2.html](https://github.com/hephaex/js/blob/master/02_css/css17-2.html)
 - wait
  - [css17-3.html](https://github.com/hephaex/js/blob/master/02_css/css17-3.html)
 - pointer
  - [css17-4.html](https://github.com/hephaex/js/blob/master/02_css/css17-4.html)
 
## 유사 클래스를 사용해 보자
- 요소가 어떤 특정 상태를 나태낼때 사용
 - a 태그와 함께 링크에 대하여 변화를 줄때
   - a:link
   - a:visited
   - a:hover
   - a:active
   - [css18-1.html](https://github.com/hephaex/js/blob/master/02_css/css18-1.html)
 - h1 태그에 위치하면 색상을 바꾸고 싶을 때
   - h1:hover {background: yellow;}
   - [css18-2.html](https://github.com/hephaex/js/blob/master/02_css/css18-2.html)
 - 입력시 강조하고 싶을 때
   - input:focus {background: green;}
   - [css18-3.html](https://github.com/hephaex/js/blob/master/02_css/css18-3.html)
- ex)
```
    a:link {color: blue;}
    a:visited {color:gray;}
    a:hover {font-weight: bold;}
    a:active {background: red;}
    h1:hover {background: orange;}
    input:focus {backgroud: green;}
```
