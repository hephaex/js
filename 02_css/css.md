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

