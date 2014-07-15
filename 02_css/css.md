# css
- Cascading sytle Sheet
- HTML 문서구조 + CSS(형식) = web페이지
- CSS 3

## 기본구성
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

#### 예시
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

```css3-1.html
<head>
  <title>CSS example</title>
  <style>
    h1 { color: red;}
  </sytle>
</head>
```

### 인라인
```ocss3-2.html
<p style="color: green;"> 안녕하세요 </p>
```

- 외부 파일
default.css를 링크를 걸어서 사용한다.
<head> ... </head>안에 넣어서 사용한다. 
<link rel="sytlesheet" href="default.css">

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
- css4-1.html
- 모든 셀렉터를 의미
- 모든 것을 빨강색으로 만듬.
>  '*'' { color: red;}

#### a, b
- css4-2.html
- 복수를 셀렉터를 설정할수 있다. 
- h1 과 h2를 모두 빨강색으로 만듬.
> h1, h2 {color: red;}

#### a b
- css4-3.html
- 섹션의 바로 아래 아이템만 설정
> section .item {color: red;}

#### a > b
- css4-4.html
- a섹션의 바로뒤 b요소를 설정
> section > .item {color:red;}

#### a + b
- css4-5.html
- a섹션의 바로뒤 b요소를 설정
- select id="main" 에서 가장 가까운 item만을 빨강색으로 만듬.
> h2 + p {color:red;}

#### a * b
- css4-6.html
- p요소중에 b구성요소를 설정
  - p item으로 지정한 것만 빨강색으로 만듬.
> p.item { color: red;}
