# CSS3
- 다양한 표현이 가능해짐.
- W3C [W3C](http://www.w3c.org)
- w3c 규정이 진행중
- 각 브라우저에 따라서 기능이 제한될 수 있음.

## 벤터 프리픽스
- 규정으로 정해지기 전에 요소를 말함
 - webkit- : chrome / safari
 - moz-    : firefox
 - o-      : opera
 - ms-     : ie
- 예시
 - border-radius: 5px;
 - webkit-border-radius: 5px;
- 대응상태 확인 [caniuse.com](http://www.caniuse.com)
- 예시 [css3-1.html](https://github.com/hephaex/js/blob/master/03_css3/css3-11.html)
```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8">
    <title> CSS3 공부 </title>
    <style>
      div {
      width : 100px;
      height : 100px;
      padding : 10px;
      margin: 30px;
      background-color: orange;
      border: 2px solid orangered;
      border-top-right-radius : 30px;
      }
    </style>
  </head>
  <body>
    <div id="test1"> test1 </div>
  </body>
</html>
```

## 원형 각호를 만들어 보자.
- border-radius : 10px;
 - 네 꼭지점 모두 각호를 생성
 - [css3-1.html](https://github.com/hephaex/js/blob/master/03_css3/css3-1.html)
- border-radius : 10px 20px 30px 40px;
 - 네 꼭지점을 시계방향으로 각호 크기를 설정
 - [css3-2.html](https://github.com/hephaex/js/blob/master/03_css3/css3-2.html)
- border-top-right-radius : 30px;
 - 우측 상단만 각호를 설정
 - [css3-3.html](https://github.com/hephaex/js/blob/master/03_css3/css3-3.html)

- border-radius : 50%;
 - 네 모서리가 둥근 박스가 됨
 - [css4-1.html](https://github.com/hephaex/js/blob/master/03_css3/css4-1.html)
- backgroud-image:url('baby.jpg');
  - 두가지를 혼용한 것으로
  - 원형이 된 것에 아이 그림이 표시됨
 - [css4-2.html](https://github.com/hephaex/js/blob/master/03_css3/css4-2.html)

## 색 지정과 투명화
- 색의 지정방법과 요소의 투명화
- css  rgb  '#ff0000' 으로 사용
- css3 rgba "#ff000007' 로 사용.
  - 혹은 background-color: rgba(0,0,0,0.7);
  - [css5-1.html](https://github.com/hephaex/js/blob/master/03_css3/css5-1.html)
- 투명도
  - opacity: 0.0 ~ 1.0; 까지 투명도 지정
  - [css5-2.html](https://github.com/hephaex/js/blob/master/03_css3/css5-2.html)

## box 요소를 꾸미기
- box-shadow : 10px 20px;
  - 박스의 그림자를 표시
  - [css6-1.html](https://github.com/hephaex/js/blob/master/03_css3/css6-1.html)  
- box-shadow : 10px 20px 5px;
  - 마지막 5px는 보캐 효과
  - [css6-2.html](https://github.com/hephaex/js/blob/master/03_css3/css6-2.html)  
- box-shadow : 10px 20px 5px rgba(0,0,0,0.3);
  - 그림자의 투명도를 지정할 수 있음.
  - [css6-3.html](https://github.com/hephaex/js/blob/master/03_css3/css6-3.html)
- box-shadow : 10px 20px 5px 20px rgba(0,0,0,0.3);
  - 그림자의 두께를 표시할 수 있음. (네번째의 20px) 
  - [css6-4.html](https://github.com/hephaex/js/blob/master/03_css3/css6-4.html)
- box-shadow : 10px 20px 5px rgba(0,0,0,0.3) inset;
  - 그림자가 반전되어 표시
  - [css6-5.html](https://github.com/hephaex/js/blob/master/03_css3/css6-5.html)
- box-shadow : 10px 20px 5px rgba(0,0,0,0.3) inset, 
                5px 5px  5px red;
  - 다중 효과 지정도 가능함.
  - [css6-6.html](https://github.com/hephaex/js/blob/master/03_css3/css6-6.html)
  
## 문자에 그림자를 넣어 보자.
- text-shadow: 5px 5px 3px red;
 - 빨간색 그림자가 생김.
 - [css7-1.html](https://github.com/hephaex/js/blob/master/03_css3/css7-1.html)
- text-shadow: 5px 5px 3px red, 10px 10px 3px blue;
 - 빨간색과 파란 그림자가 생김.
 - [css7-2.html](https://github.com/hephaex/js/blob/master/03_css3/css7-2.html)
- text-shadow: 1px 1px 0px white, 2px 2px 0 black;
 - 까망과 하얀 그림자가 생김.
 - [css7-3.html](https://github.com/hephaex/js/blob/master/03_css3/css7-3.html)
 
## 문자에 그라데이션을 넣어 보자.
- background: -webkit-linear-gradent();
- background: linear-gradient(red 10%,yellow 90%, blue 10%);
 - [css8-1.html](https://github.com/hephaex/js/blob/master/03_css3/css8-1.html)
- background: linear-gradient(red 10px, yello 90px, blue);
 - [css8-2.html](https://github.com/hephaex/js/blob/master/03_css3/css8-2.html)
- background: linear-gradient(right top, red, blue);
 - [css8-3.html](https://github.com/hephaex/js/blob/master/03_css3/css8-3.html)
- background: linear-gradient(45deg, red, blue);
 - [css8-4.html](https://github.com/hephaex/js/blob/master/03_css3/css8-4.html)
- background: radial-gradient(red,blue);
 - [css9-1.html](https://github.com/hephaex/js/blob/master/03_css3/css9-1.html)
- background: radial-gradient(red,yellow,blue);
 - [css9-2.html](https://github.com/hephaex/js/blob/master/03_css3/css9-2.html)
- background: radial-gradient(top right,red,yellow,blue);
 - [css9-3.html](https://github.com/hephaex/js/blob/master/03_css3/css9-3.html)
- background: radial-gradient(10px 10px,circle contain,red,yellow 90%);
 - [css9-4.html](https://github.com/hephaex/js/blob/master/03_css3/css9-4.html)

## 요소를 변형해 보자.
- caniuse.com 에서 transform 을 확인하면 -webkit-으로 머릿말을 붙이라고 한다. 
 - [css10-1.html](https://github.com/hephaex/js/blob/master/03_css3/css10-1.html)
- 가로/세로 크기 변화 : 
  - scale (1.2 가로축, 1.5 세로축) 크기 변화
  - -webkit-transform: scale(1.2,1.5);
  - [css10-2.html](https://github.com/hephaex/js/blob/master/03_css3/css10-2.html)
- 가로만 크기 변화 : 
  - -webkit-transform: scaleX(1.2);
  - [css10-3.html](https://github.com/hephaex/js/blob/master/03_css3/css10-3.html)
- 세로만 크기 변화 : 
  - -webkit-transform: scaleY(1.2);
  - [css10-4.html](https://github.com/hephaex/js/blob/master/03_css3/css10-4.html)
- Z축만 크기 변화 : 
  - -webkit-transform: scaleZ(1.2);
  - [css10-5.html](https://github.com/hephaex/js/blob/master/03_css3/css10-5.html)
- 원점을 바꾸어 보자.
  - -webkit-transform: origin: 0 0;
  - -webkit-transform: scale(1.2, 1.5);
  - [css10-6.html](https://github.com/hephaex/js/blob/master/03_css3/css10-6.html)
- 3차원 크기 변화 : 
  - -webkit-transform: scale3d(1.2, 1.5, 1.7);
  - [css10-7.html](https://github.com/hephaex/js/blob/master/03_css3/css10-7.html)
- 중심축을 바꾸어 보자.
  - -webkit-transform-origin: top left;
  - -webkit-transform-origin: 10px 10px;
- X축으로 이동
  - -webkit-transform: translateX(20px);
  - [css11-1.html](https://github.com/hephaex/js/blob/master/03_css3/css11-1.html)  
- X축, Y축으로 이동
  - -webkit-transform: translate(20px, 100px);
  - [css11-2.html](https://github.com/hephaex/js/blob/master/03_css3/css11-2.html)
- 45도 회전
  - -webkit-transform: rotate(45deg);
  - [css11-3.html](https://github.com/hephaex/js/blob/master/03_css3/css11-3.html)
- skewX : X축으로 찌그러지기
  - -webkit-transform: skewX(45deg);
  - [css11-4.html](https://github.com/hephaex/js/blob/master/03_css3/css11-4.html)
- skew : x축,Y축으로 찌그러지기
  - -webkit-transform: skew(45deg, 20deg);
  - [css11-5.html](https://github.com/hephaex/js/blob/master/03_css3/css11-5.html)
  
## 애니메이션을 넣어 보자.
- [css12-1.html](https://github.com/hephaex/js/blob/master/03_css3/css12-1.html)
- 변화할 방향지정
  - transition-property:all;
- 변화할 기간
  - transition-duration: 1s;
- 변화 방법
  - transition-timing-function:ease;
  - /* linear, ease-in, ease-out, ease-in-out */
  - [css12-2.html](https://github.com/hephaex/js/blob/master/03_css3/css12-2.html)
- 한번에 쓸 경우
  - translation: all 1s ease 2s;
  - [css12-3.html](https://github.com/hephaex/js/blob/master/03_css3/css12-3.html)
  
## 키 프레임을 사용한 애니메이션
- animation 이라고 설정해 놓고.
 - animation-name: animationTest;
 -  animation-duration: 5s;
 -  animation-timing-function: ease;
 -  animation-delay: 1s;
 -  animation-iteration-count: infinite;
 -  animation-direction: normal / alternate
 - -webkit-animation: animationTest 5s ease 1s infinite normal;

- @-webkit-keyframes animationTest로 해서 지정한다. 
```
    @-webkit-keyframes animationTest{
    0% {width: 50px; background: orange;}
    50% {width: 100px; background: blue;}
    100% {width: 200px; background: yellow;}
    }
```
- [css14.html](https://github.com/hephaex/js/blob/master/03_css3/css14.html)

## 속성 셀렉터를 사용해 보자
```
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="utf-8">
  <title> CSS3 공부 </title>
  <style>
    a[href="http://dotinstall.com"] {
     color:yellow;
    }
  </style>
</head>
<body>
  <h1> links </h1>
  <ul>
    <li> <a href="http://dotinstall.com">dotinstall.com</a></li>
    <li> <a href="http://google.com">google.com</a></li>
    <li> <a href="http://yahoo.co.jp">yahoo.co.jp</a></li>
    <li> <a href="mailto:hephaex@gmail.com">mail to me</a></li>
  </ul>
</body>
</html>
```
- <style> </style>에서 속성을 지정한다.
- 예시 1 (특정)
```
     a[href="http://dotinstall.com"] {
     color:yellow;
    }
```
- 예시 2 (전부)
```
     a[href*="com"] {
     color:yellow;
    }
```
- 예시 3 (전방참조)
```
     a[href^="http"] {
     color:yellow;
    }
```
- 예시 4 (후방참조)
```
     a[href$="jp"] {
     color:yellow;
    }
```
- [css15.html](https://github.com/hephaex/js/blob/master/03_css3/css15.html)

