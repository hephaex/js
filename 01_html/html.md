# HTML
- 홈페이지를 위해서 사용하는 언어
- Hyper Text Mark up Language

## 범위
- HTML5
- 브라우저 확인 [caniuse.com](http://www.caniuse.com) 지원하는 브라우저를 확인가능

## 필요한 도구
- 텍스트 에디터
- 크롬 브라우져

# HTML의 개요
- HTML은 태그로 구성된다.

## 태크
- <태그>
- <태그 속성="값">
- <태크> Text </태그>


## 처음 만드는 HTML　문서
``` 1st.html
<!DOCUTYPE HTML>
<HTML LANG='KO'>
  <HEAD>
    <META CHARSET="UTF-8">
    <TITLE>처음 만든 HTML</TITLE>
  </HEAD>
  <BODY>
    <P>안녕하세요.</P>
  </BODY>
</HTML>
````
브라우저를 열어서 *1st.html*을 연다.
HTML5의 확장자는 html이된다.

## 기본적인 태크를 배워보자
- <!DOCUTYPE html>
  - HTML 문서라는 것을 나타냄.
- <html langG='KO'>
  - 사용언어가 ko라는 속성을 정의함
- <HEAD>
  - 머릿말을 나타냄
  
- <META CHARSET="UTF-8">
  - 문자코드를 나타냄
  
- <TITLE>처음 만든 HTML</TITLE>
  - 문서의 타이틀
- </HEAD>
  - 머릿말을 닫는 태그
- <!--    -->
  - 코멘트를 적는데 사용함
- <BODY>
  - 본문을 나타냄
- <P>안녕하세요.</P>
- </BODY>
  - 본문을 닫는 태그
- </HTML>
  - 문서를 닫는 태그

## <head>　에 사용하는 태그
- <meta>
 - <meta name="description" content="처음으로 만든 HTML문서 입니다. ">
 - 문서에 대한 설명을 나타냄
 - 검색엔진등에서 검색하여 표시되는 문서에 대한 개요임
- <sytle>
``` <style>
<style>
 p { color: red ; }
</style>
```
 - <link rel="styesheet" href="mystyle.css">
   - 별로문서로 만드는 경우도 많음.
 - <link rel="shotcut icon" href="favicon.ico">
   - 바로가기 아이콘을 별도 스타일 문서로 저장해서 읽어올때

## <body＞에 사용하는 테그
- <h1> 크게 </h1>
- <h2> 중간 </h2>
- <h3> 작게 </h3>
- <h4> , <h5>, <h6> 까지 있음.
- <br>
 - 문장의 줄바꾸기에 사용.
- <strong> </strong>
 - 강조
- <hr>
 - 페이지 나움
- <ul> 항목 표시 (점)
 - unordered list
```
    <ul> <!-- Unordered List -->
      <li>Apple</li> <!-- List Item -->
      <li>Banana</li>
    </ul>
```
- <ol> 항목 표시 (숫자)
 - ordered list
```
    <ol> <!-- Ordered List -->
      <li>Apple</li> <!-- List Item -->
      <li>Banana</li>
    </ol>
```

## table 태그
```
  <body>
    <!-- 
     tr : table row 
     th : table header
     td : table data
    -->
    <table>
      <thead>
	<tr><th>name</th><th>2010</th><th>2011</th></tr>
      </thead>
      <tbody>
	<tr><td>@adam</td><td>200</td><td>210</td></tr>
	<tr><td>@brawn</td><td>300</td><td>420</td></tr>
	<tr><td>@Charrie</td><td>500</td><td>380</td></tr>
      </tbody>
    </table>
  </body>
```

## link
<a href="http://www.google.com">Google</a>
 - 외부 링크를 열때
<a href="http://www.google.com" target="_blank" >Google</a>
 - 별도의 탭으로 열때
<a href="hello.html">Hello</a>
 - 다른 html　문서를 열때.
<a href="#hello2">hello2</a>
 -　내부 이동
 - 이동할 위치 <p id="hello2">hello2</p>

## 그림표시
<img>
<img src="cart.jpg">
<img src="cart.jpg" width="500" height="283">
<img src="cart.jpg" width="500" height="283" alt="cart">
 - alt는 문자 표시일때 설명
 <img src="cart.jpg" width="500" height="283" alt="cart" title="cart picture">

## form 태크로 형식을 만들자.
- 입력을 하는 것
```
<form action="survey.php" method="post">
 <p>이릅:<input type="text" name="name" size="60" maxlength="5"> </p>
 <p>메모:<textare name="memo" name="name"> </p>
 <p><input type="submit" value="송신"> </p>
</form>
```

## 다양한 입력
```
<form action="survey.php" method="post">
  <p>이릅:<input type="text" name="name" size="60" maxlength="5" required> </p>
  <p>이릅2:<input type="text" name="name2" required> </p>
  <p>암호:<input type="password" name="password"> </p>
  <p><input type="hidden" name="user_id" value="32"> </p>
  <p>일시 :<input type="date" name="birthday"> </p>
  <p>url  :<input type="url" name="url"> </p>
  <p>email:<input type="email" name="email"> </p>
  <p><input type="submit" value="송신"> </p>
</form>
```
- required : 입력을 반드시 할것
- input type
  - text
  - password
  - date
  - url
  - email
  - hidden

## radio checkbox, label
```
<p> <!-- radio 로 한가지만 선택 되게 -->
  colors:
  <input type="radio" name="color" value="red">Red
  <input type="radio" name="color" value="blue">blue
  <input type="radio" name="color" value="green">green
</p>
<p> <!-- label을 눌러도 선택이 되게-->
  colors:
  <label><input type="radio" name="color" value="red">Red</label>
  <input type="radio" name="color" value="blue" id="blue">blue<label for="blue">blue</lable>
  <label><input type="radio" name="color" value="green">green</label>
</p>

<p> <!-- checkbox 여러개가 선택가능 -->
  colors:
  <input type="checkbox" name="color" value="red">Red
  <input type="checkbox" name="color" value="blue">blue
  <input type="checkbox" name="color" value="green">green
</p>
```

## select
```
<form action="survey.php" method="post">
      <select name="color" size="5" multiple>
	<option value="red">red</option>
	<option value="blue">blue</option>
	<option value="green">green</option>
      </select>
      <p><input type="submit" value="send"></p>
</form>
```

## div, span과 id,class
```
    <!-- 
     sylying
     div: 범용 블록 요소 (전후에 개행이 들어감)
     span: 범용 인라인 요소 (전후에 개행이 들어가지 않음)
    
     id : 문서에 한개뿐인 요소에 사용
     class : 복수 요소 사용가능
     -->
    <div id="main">
      <p> 안녕하세요.</p>
      <p> 안녕하세요.<span class ="notice">안녕하세요.</span></p>
    </div>
    <p> 안녕하세요.<span class ="notice">안녕하세요.</span></p>
    <p> 안녕하세요. 안녕하세요.</p>
```

## 문장 구조를 나타내는 태그
```
    <!-- 
     sylying
     div: 범용 블록 요소 (전후에 개행이 들어감)
     span: 범용 인라인 요소 (전후에 개행이 들어가지 않음)
    
     id : 문서에 한개뿐인 요소에 사용
     class : 복수 요소 사용가능
     
　　　구조
     header
     footer
     nav
     article
     aside
     section
      -->
    <header>
      <h1> 일기 </h1>
      <nav>
	home
	profile
      </nav>
    </header>
    <article>
      <h2>릴리즈 완료</h2>
      <p> 기쁘다!!!</p>
      
      <aside>
	<h3>이 사이트는</h3>
	<p>    @hephaex　의 일기</p>
	
      </aside>
      <footer>
	<p> copyright 2014 hephaex </p>
      </footer>
```
이전인 경우는
```
<div id="header">
      <h1> 일기 </h1>
	home
	profile
</div>
```

## 실전 참조 sytle, script
```
    <!-- 
     실체 참조
     sytle 구성
     script
      -->
    <p> 실제 참조의 예시 </p>
    <p> 이것은 <p> 입니다. </p>
    <p> 이것은 &lt;p&gt;입니다</p>
    <p> 스타일 속성</p>
    <p style="color:red;">안녕하세요.</p>
    <p> script </p>
    <script src="myscript.js"></script>
```