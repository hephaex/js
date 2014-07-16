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
