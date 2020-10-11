# cocoa-web

> 다시하는 코코아클론웹

> 마크다운으로 복습내용정리할것!

> 폴더이름과 파일이름은 꼭 소문자로 작성할 것!

  

---

  

# 웹의 구성요소

  

1. HTML

- 텍스트와 그림, 링크로 이루어진 웹의 뼈대

2. CSS

- HTML과 반드시 함께 쓰이며 텍스트를 꾸며주는 디자인 언어. 웹의 근육

3. JavaScript

- 웹을 동적으로 만들어주는 프로그래밍 언어 웹의 뇌에 해당한다.

- 동적이란? 유튜브처럼 클릭을 하면 어딘가로 이동하거나 무언가를 보여줌.

  

---

  

# HTML tags

  

### a (앵커)

  

예시-구글로 이동

`<a href="https://google.com" target="_self">GO to Google</a>`

  

| `_self` | `_blank` |
| ------- | -------- |
| 현재 창 | 새 창 |

`_self`는 target의 default이다.

---
### 이미지 삽입시 폴더 경로설정
```html
<img src="picture.jpg"/>
<img src="folderName/picture.jpg"/>
삽입할 사진이 다른 폴더에 있을 경우에는
폴더경로를 꼭 기재해야한다!
```
___
### meta태그 이것저것
```html
<meta charset="UTF-8"/>
한글이나 특수문자를 웹이 이해할 수 있게
번역하여 글자깨짐을 방지해준다.
```
```html
<meta name="description" content="스마트 TV, 태블릿, 스마트폰, PC, 게임 콘솔 등 다양한 디바이스에서 영화와 TV 프로그램을 마음껏 즐기세요." />
구글에서 검색할 때 content 안의 내용이 보여지게된다.
```

```html
<meta property="og:title" content="Nomad Coders">
<meta property="og:type" content="website">
<meta property="og:url" content="https://nomadcoders.co/">
<meta property="og:image" content="pictureNameOrAddress.jpg">
<meta property="og:description"content="코딩은 진짜를 만들어보는거야!.">
<meta property="og:site_name" content="Nomad Coders">
<meta property="og:locale" content="ko_KR">
```
meta property __open graph(줄여서 og)__ 는 카카오톡에 특정링크를 전송했을때 띄어지는 미리보기다.
[![meta og 예시](https://img1.daumcdn.net/thumb/R800x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F1hkKC%2FbtqC78M8NMg%2F6cG5iXuxXcqxpGa7cwaRx0%2Fimg.png)](https://ddorang-d.tistory.com/31)
___
### body태그 lang attribute
```html
<body lang="kr"></body>
주된 언어가 어떤 언어인지 브라우저에게 
알려준다.
```
___
### 브라우저 타이틀 옆 로고(short cut icon)
```html
<link rel="shortcut icon" size="16x16 32x32 16x16" href="logoPicture.jpg">
브라우저 타이틀 옆 조그만 로고넣을 때 사용
```

---
### form에서 가끔 쓸 attribute
1. type="color", "email", "url", "range", "date" 등등...
2. disabled
3. required
4. minlength="10"
5. accept="image/*, .pdf"

```
<label for="profile">Seongchan</label>
<input id="profile" type="file" required/>
라벨의 for과 input의 id는 값이 똑같아야한다.
```	 
---
### Semantic tag
semantic tag란? div와 동일한 박스기능을 하지만 태그이름만으로 그 태그가 어떤 내용인지 알 수 있게 해주는 태그
코드를 div로 떡칠하는걸 방지하고 읽는사람이 편하게해줌
>`<header>`
>`<main>`
>`<footer>`
>`<nav>`
>`<address>`
등등등...

___
### 블록과 인라인 element는 뭐가 있을까
__대표적인 `inline element`는 a, img, span, code가 있다.__
**대부분은 `block element`라서 `inline element`를 조금 알고 그 나머지는 전부 블록이라고 알고있는게 좋다.**
___
### block과 inline의 margin, border, padding
inline 요소는 width와 height를 가질 수 없다.
margin은 border경계의 바깥쪽 구역을 말한다.
padding은 border경계의 안쪽 구역을 말한다.

__margin과 padding을 주는 방식__
```css
margin:20px
margin-top:20px
margin: 20px 30px //상하 좌우`
margin: 2px, 3px, 5px, 8px //상 우 하 좌(시계방향) 
```
**collapsing margins 현상 꼭 기억할것!**
	+부모 박스의 상하 경계가 자식 박스의 상하경계와 맞닿을때 margin이 하나로 통일된다. 상하에만 적용되고 좌우에는 적용이 되지 않는다.
[![collapsing margins](https://i.stack.imgur.com/is2BD.png)](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)
\*추가*\
블록끼리 가진 마진의 방향이 같을 때 값이 큰 마진만 적용되고 나머진 다 씹히는 현상도 있더라. 자세한건 밑 링크참고
[margin collapsing 설명 블로그링크](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)
 
 모든 element에 property(속성) 부여하기
 스타일태그에 *{} 적으면 됨
예시)  `*{border:"2px solid black"}` 

inline은 특별하기 때문에 일부만 적용이 되는게 더러 있다.
1. margin은 상하적용안되고 좌우만 적용됨.
2. width와 height를 가질 수 없음. 
3. padding은 다 적용 잘됨.

등등... 때문에 inline에 margin을 적용하고자 하면 display를 block으로 바꿔주어야한다.

__inline-block이란?__
inline처럼 옆에 나란히 올 수 있지만 각각 요소를 block으로 해주는 display를 말한다.  따라서 inline이 가질 수 없는 width와 height를 가질 수 있다. inline-block은 많이 쓰이지는 않는다. 왜냐하면 우리에겐 display flex가 있기때문이다.

___
## Flex box
1. __Rule 1__
	+ display flex는 기본적으로 자식을 감싸고 있는 부모태그에 적어 부모태그를 flex container로 만들며 자식태그에는 아무것도 적지 않아야한다.

2. __Rule 2__
	+ justify-content==main axis
	
	+ align-items==cross axis
		![flex-direction](https://cms-assets.tutsplus.com/uploads/users/30/posts/30183/image/axes.png)

	+ flex-direction으로 이 둘을 반전시킬 수 있다.
		+ flex-direction default는 row 반전은 column
		+ row-reverse는 좌우 반전 column-reverse는 상하반전

	+ 예)  justify-content:"space-between" flex-direction="column"

flex stretch(쭉 늘리기)와 wrap(창 사이즈 줄일시 도형 합치기?)도 있었다.

___
### position fixed

상단 메뉴바 처럼 특정 요소의 위치를 고정시킨다. 
fixed를 쓴 후 top, bottom, left, right중 어느 한 값이라도 주게되면 레이어가 분리되어 서로 겹칠 수 있게 된다.
![fixed](https://media.vlpt.us/images/realryankim/post/a4aa7fe6-00ca-4cbf-89de-12be6eb374a3/blog-15-03-1.png)
	
### position static
position의 default로 레이아웃이 박스를 처음 위치시켜주는 곳
### position relative
어떤 요소를 현재위치에서 아주 조그만 움직이고 싶을 때 사용한다. 이때 처음위치를 기준으로 옮기게된다.*__위 그림 참고!__*
### position absolute
가장 가까운 relative 부모를 기준으로 위치를 옮겨준다.
요소를 absolute해주고 부모에 relative가 없으면 body를 기준으로 움직이게 된다. body는 기본적으로 relative기 때문이다.
___

## pseudo selector

class나 id없이 특정 요소를 가리키는 법
```css
1. div:first-child{css code}
2. div:last-child{css code}
3. div:nth-child(1 or 2.. 지정하고 싶은 요소의번호){css code}
4. div:nth-child(2n or 3n+1.. 3n은 3번째부터 3칸간격으로 css코드적용 3n+1은 첫번째 css적용 후 다음 3번째칸 css코드 적용 ){css code}
5. div:nth-child(even or odd 짝수또는 홀수번호 지정){css code}
```
:first-child, last-child, nth-child는 형제태그 중 첫번째, 마지막, 지정한 번수째 태그를 가리킨다.
### 부모태그의 자식태그 중 하나만 지정하기
```html
<div>
	<span>hello</span>
	<p>이것은 예시 html코드이다.<span>hello</span></p>
</div>
```
위  html코드에서 p태그 안 span만 css를 적용시키위해 지정하려면 어떻게 해야할까? 아래코드를 보자.
```css
div p span{
	background-color:tomato;
}
div 안 p 안 span을 찾아 css를 적용시켜준다.
```
위 css코드처럼 부모태그의 특정헌 자식태그를 지정할 수 있다.
아래에 나온 태그는 부모태그 바로 밑 태그를 지정하는 코드다.
```css
div>span{
	background-color:tomato;
}
```
\>, <(대소)기호로 부모태그(여기선 div)바로 밑 자식태크를 지정할 수 있다.
또한 아래 코드는 특정 태그의 형제태그를 지정하는 방법이다.
```css
p+span{
	background-color:tomato;
}
p태그 바로 밑에오는 span태그만 지정할 수 있다.
```
바로 밑에 오진 않으나 형제태그를 지정하고싶을때는 ~기호를 쓴다. 아래코드를 보자.
```css
p~span{
	background-color:tomato;
}
p태그의 바로 밑에 오지않아도 형제태그이면 지정할 수 있게한다.
```
___
### attribute를 이용한 optional
```html
<form>
	<input type="text" placeholder="username" required />
	<input type="password" placeholder="username"/>
</form>
```
 attr이 required인 input만 css를 적용시키고 싶다면
 ```css
 input:required{
	border-color:red;
}
```
type이 password인 것을 지정하고싶다면?
```css
 input[type="password"]{
	border-color:red;
}
```
placeholder 역시 사용할 수 있다.
```css
 input[placeholder="username"]{
	border-color:red;
}
```
placeholder에 name이라는 글자가 포함된 것들을 모두 지정하고싶다면? 물결표시를 쓰면 된다 ~=는 포함하고있다 라는 뜻이다.
```css
 input[placeholder~="username"]{
	border-color:red;
}
```
## states
hover, focus, active, focus-within, visited 등이 있다.
hover = 마우스를 요소위에 올렸을때 작동
focus = 키보드로 요소를 선택했을 때 작동
focus-within = 키보드로 특정요소의 자식태그를 선택했을 때 작동(자식태그가 지정되면서 부모태그가 변한다!)
active = 마우스로 요소를 클릭했을 때 작동
visited = 링크를 방문했을 때 작동
코드 예시)
```css
input:hover{css code}
input:active{css code}
input:focus{css code}
input:focus-within{css code}
input:visited{css code}
```
여러가지 응용 예시를 보자.
```html
<form>
	<input type="text"/>
	<input type="text"/>
	<input type="text"/>
</form>
```
html코드가 위와 같을 때 이렇게 쓸 수 도 있다.
```css
form:focus-within input{css code}
form:hover input:focus{css code}
```
여러 조건을 섞어서 쓸 수 있다. 첫번째 코드는 focus-within으로 form의 자식태그인 input이 focus가 되면 원래 부모태그인 form이 변해야하나 마지막에 input이 있어 input이 변하게된다. 즉 form의 자식태그인 input이 focus되면 input이 변하게된다.
두번째 코드의 경우 form에 마우스가 올라감과 동시에 input에 focus가 되어야 작동한다.

항상 가장 우측에 있는 코드가 css코드의 적용대상이 되고
왼쪽에 있는 것들은 조건이 된다.
### 기타 다른 states
__`p::placeholder{css code}`처럼 콜론을 두번 써준다.__
1. placeholder = input type="text"안 글자를 꾸밀수 있게해준다.
2. selection = 타이핑 한 글자를 드래그했을때 색상 등을 꾸밀 수 있음
3. first-letter, first-line = 첫번째 글자, 첫번째 문장을 꾸밀 수 있게 해준다.

___
### color

>**color 넣는 법**
`color:#fcce00;`
`color: blue;`
`color: rgb(red, green, blue);`
`color: rgba(red, green, blue, opacity);`

### 색깔을 변수처럼 지정하는 방법 root
css에는 변수가 없지만 변수와 비슷한 기능을 하는 root가 있다. 아래 예시를 보자!
 먼저 root를 정의한다.
```css
:root{
	--main-bgcolor:#fcce00;
	--default-border:1px solid rgba(0,0,0,0.5);
	--special-border:1px solid var(--main-bgcolor);
}
이름을 적을 때 앞에 --두개의 대쉬를적어주고, 빈공간은 하나의대쉬로 채워주어야한다.
```
그 후 var을 통해 root를 적용시킨다.
```css
body{
	background-color:var(--main-bgcolor);
}
```	
**root를 쓰면 일일이 css를 수정하지 않아도 된다. 마치 변수처럼 말이다.**
___
## Transitions
소스코드
```css
a{
color: black;
background-color: tomato;
padding:  5px  3px;
border-radius:  3px;
text-decoration:  none;
transition:background-color 10s ease-in-out, color 10s ease-in-out;
}
```
__transition은 a:hover에 있는 것만 적용시킬 수 있다.__
__transition은 반드시 a처럼 element가 처음생겨난 곳에 위치해야 한다.__ a:hover안에 transition을 적을 경우 마우스를 올린동안만 transition이 작동하기 때문!
```css
a:hover{
	background-color:blue;
	color:white;
}
```
transition: 첫번째, 바꿀 효과 이름, 두번째, 시간 세번째, 변화속도
transition에 all을 줄 수도 있다.
```css
transition: all 10s ease-in-out
```
이렇게 하면 a:hover에 있는모든것들을 변화시킬 수 있다.
또한 hover이 아닌 active나 focus 등 다른 state도 적용시킬 수 있다.

transition은 색깔 외에도 border, radius, font-size 등 다양한 것들에 적용시킬 수 있지만 반드시 a:hover처럼 state안에 border같은 변화시키고자 하는코드가 존재해야한다.

### ease-in-out
transition 중 ease-in-out은 가속도를 의미한다.
ease, ease-in-out, linear등 여러가지 default값을 가지고 있다.(자세한 건 [ceaser 홈페이지 참고](https://matthewlein.com/tools/ceaser))
또한, 아래와 같이 cubic-bezier을 통해 직접 가속도를 작성할 수 도 있다.
`transition : all 3s cubic-bezier(0.600, 0.040, 0.980, 0.335);`

___
__border-radius에 50%를 주면 border가 원이된다.__
___
## Transform
사용 예시)
`transform:  rotateX(45deg)  rotateY(30deg);`
가운데에 쉼표 안쓰는듯
만약 
```css
transform:  translateY(-5px);
transform:  rotateY(360deg);
위 처럼 transform을 따로따로 쓰면 겹쳐져서 맨 아래 transform만 적용되게 된다. (css는 cascading인 것에 유의)
또다른 예로는
transform:  translateY(-5px), rotateY(360deg);
쉽표 또한 정상적인 기능을 하지 못하게 한다. 쉼표없이 그냥 띄어쓰기만 할 것.
```

트랜스폼을 적용시키고자 하는 element에 css로 작성해야한다.
```css
img  {
width:  300px;
height:  300px;
border:  2px  solid  black;
border-radius:  50%;
transition: transform 2s  ease-in-out;
}
```
```css
img:hover  {
transform:  rotateZ(90deg);
}
```
 __transform의 translate는 block이나 inline에 상관없이 입력한만큼 움직인다.__ 즉, 다른 element와 겹칠 수 있다는 소리. 다른 픽셀상에서 일어나기때문이란다.
 ![transform](https://miro.medium.com/max/1440/1*_NVMTnvHTM9teQxrVRlDeg.png)

### transition과 transform의 조화

```css
img  {
width:  300px;
height:  300px;
border:  2px  solid  black;
border-radius:  50%;
transition: transform 2s  ease-in-out;
} 
img:hover  {
transform:  rotateZ(90deg);
}
```
transform을 준뒤에 transition으로 서서히 바뀌게 함.
__명심할 것!__ transition은 state가 아닌 root에 있어야한다.
만약 state에 transition을 준다면 hover의 경우 마우스를 올려놓은 상태에서는 transition이 작동하나, 떼는 순간 원상태로 돌아가버린다.

### @keyframes 
css에서 작성한다.
```css
@keyframes  coinFlip  {
	from {
	transform:  rotateY(0deg)  translateX(0px);
	}
	to {
	transform:  rotateY(180deg)  translateX(100px);
	}
}
img  {
width:  300px;
height:  300px;
border:  2px  solid  black;
border-radius:  50%;
animation: coinFlip 2s  ease-in-out  infinite;
}
```
animation을 @keyframes를 통해 직접 만든 후 root에 animation을 주면 된다. infinite는 해당효과를 계속 반복시켜준다. forwards는 keyframes의 마지막 효과를 유지한다.
`animation: coinFlip 2s  ease-in-out  forwards;`

### animation-delay
`animation-delay:  0.5s;`
animation 시작을 내가 적은 값만큼 늦춰준다.
__딜레이는 처음 시작할 때만 적용이 되며 infinite를 이용했을 때 두번째 재생부터는 적용이 되지 않는다.__


from~to는 곧 0%~100% 진행을 말하며 이를 내가 원하는 대로 바꿔줄 수 있다.
```css
@keyframes coinFlip{
0% {
transform:  rotateY(0deg)  translatey(0px);
}
25% {
transform:  rotateY(360deg)  translateY(-100px);
border-radius:  0%;
border-color:  red;
}
50% {
transform:  rotateY(0deg)  translatey(0px);
}
75% {
transform:  rotatey(360deg)  translatey(100px);
border-width:  10px;
border-color:  blue;
}
100% {
transform:  rotateY(0deg)  translatey(0px);
}
}
```
반복 재생하되 재생이 될 때 딜레이를 주고 싶다면
키프레임 애니메이션 코드 마지막에 transform을 유지하는 부분을 넣어주면 된다. 물론 infinite를 넣어주어야 반복재생됨을 잊지말자.
예시) 
```css
/* animation code start */

@keyframes  circle-spin {
0%{
	transform:  rotateZ(0deg);
}33%{
	transform:  rotateZ(180deg);
}66%{
	transform:  rotateZ(180deg);
}100%{
	transform:  rotateZ(180deg);
}
}

@keyframes  volume-wave{
0%{
	transform:  scaleY(1);
}33%{
	transform:  scaleY(2);
}66%{
	transform:  scaleY(1);
}100%{
	transform:  scaleY(1);
}
}
/* animation code end */
```
___
## @mediaquery
화면 크기에 따라 화면에 변화를 줄 수있다,
사용 예시)
```css
@media  screen  and  (min-width:  1000px)  {
div  {
background-color:  powderblue;
}  /*min-width는 ~px 이상 구역을 말함. */
}
@media  screen  and  (max-width:  600px)  {
div  {
background-color:  red;
}  /*max-width는 ~px 이하 구역을 말함. */
}
@media  screen  and  (max-width:  800px)  and  (min-width:  600px)  {
div  {
background-color:  tomato;
}  /*600px이상 800px이하 구역을 말함. */
}
```
mediaquery는 "and"로 연결되며 조건문처럼 해당 조건을 만족시켰을때 효과가 적용된다.
또한, orientation을 통해 화면의 가로 세로 모드도 구별할 수 있다.
```css
@media  screen  and  (orientation:  portrait)  {
span  {
display:  none;
}
}

@media  screen  and  (orientation:  landscape)  {
span  {
background-color:  darkgreen;
}
}
```
portrait=세로
landscape=가로
max-width:800px = 화면의 크기가800px이하일때 작동
min-width:1000px = 화면의 크기가 1000px이상일 때 작동
```css
@media  print  {
body  {
background-color:  red;
}
}
```
screen 외 여러기능이 있으나 잘 쓰이진 않으며 그 중 대표적으로 print가 있다. 해당 기능을 사용하면 프린트할때 효과를 적용시킬 수 있다.
___
### .gitignore

.gitignore은 파일이며 특정 파일을 무시하고싶을 때 이용한다.
예를 들어 readme.md를 커밋에 업로드하고싶지않을 떄 .gitignore에서 해당 파일 이름을 쓰고 저장하면 더이상 그 파일은 커밋에서 보이지 않는다!
___
### BEM

css 작성자 및 다른 사람들이 코드를 보고 각 클래스 간 어떤 상관관계가 있는지 쉽게 이해하기 위해 준수하는 작명규칙
크게 3가지로 나뉜다,

#### 블록(Block)

-   재사용 할 수있는 기능적으로 독립적인 페이지 구성 요소. HTML에서 블록은 class 속성으로 표시된다.
-   형태(red, big)가 아닌 목적(menu, button)에 맞게 결정해야 한다.
-   블록은 환경에 영향을 받지 않아야 한다. 즉, 여백이나 위치를 설정하면 안된다.
-   태그, id 선택자를 사용하면 안된다.
-   블록은 서로 중첩해서 작성 할 수 있다.
-   예) header, menu, search-form ….

```html
<div  class="header"></div>
<div  class="status-bar"></div>
<div  class="navigation-bar"></div>
```


#### 요소(Element)

-   블록안에서 특정 기능을 담당하는 부분.
-   block__element 형태로 사용 (더블 언더바)
-   형태(red, big)가 아닌 목적(item, text, title)에 맞게 결정해야 한다.
-   요소는 중첩해서 작성 할 수 있다.
-   요소는 블록의 부분으로만 사용 할 수 있고 다른 요소의 부분으로 사용할 수 없다.
-   모든 블록에서 요소는 필수가 아닌 선택적으로 사용한다. 즉 블록안에 요소가 없을 수도 있다.
-   예) menu__item, header__title …

```html
<div  class="header">
	<div  class="header__title">This is title</div>
</div>
```
#### 수식어(Modifier)

-   블록이나 요소의 모양(color, size..), 상태(disabled, checked..)를 정의한다.
-   block__element — modifier, block — modifier 형태로 사용(더블 하이픈)
-   수식어의  **블리언 타입**과  **키-벨류**  타입이 있다.
-   블리언 타입 : 수식어가 있으면 값이 true 라고 가정한다. (form__button — disabled)
-   키-벨류 타입 : 키, 벨류를 하이픈으로 연결하여 표시한다. (color-red, theme-ocean)
-   수식어는 단독으로 사용할 수 없다. 즉 기본 블록과 요소에 추가하여 사용해야 한다. ( class=”**block__element**  **block__element — modifier**”)
```html
div  class="header">
<div  class="header-bgcolor"></div>
<div  class="header-size"></div>
</div>
```
#### 혼합사용 (Mix)

-   block1, block2__element 형태로 사용할 수 있다.
-   block2__element 에 여백이나 위치를 지정하고 block1은 독립적으로 유지할 수 있다.
-   예)

```
<div class=”header”> 
	<div class=”search-form header__search-form”></div> 
</div>
```
### font-style 불러오기
css에서 작성한다.
```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap");
body  {
font-family:  "Open Sans",  sans-serif;
}
```
구글폰트에서 원하는 폰트를 import를 통해 가져오고, font-family로 사용한다.

---
## CSS hack
flex 안에 flex를 작성할 수 있다.
```css
.status-bar  {
display:  flex;
justify-content:  center;
}
.status-bar__column:nth-child(2)  {
display:  flex;
justify-content:  center;
}
```
auto를 이용한 margin 조절(kakao클론코딩 alt-header부분)
```css
.alt-header__column:first-child  {
	margin-right:  auto;
}
  
.alt-header__column:last-child  {
	margin-left:  auto;
}
```
___
`border:none;` - border를 삭제할 수 있다.
`outline:none;` input:state 에서 요소가 선택되었을 때 나오는 아웃라인을 삭제할 수 있다.
`color:inherit;` inherit는 부모로부터 상속받는 것을 말한다. color의 경우 default가 black이니 inherit가 적용된 자식태그는 부모태그의 color을 물려받아 그 색이 적용된다.
___
### css not
자주 쓰이진 않지만  not을 통해  선택 attr를 제외한 나머지 태그를 지정할 수 있다.
```css
.login-form  input:not([type="submit"])  {
	transition: border-color 0.3s  ease-in-out;
}
```
type이 submit가 아닌 다른 attr 요소들에게 transition을 준다.

___
## form action & method
```css
<form  class="login-form"  method="GET"  action="friends.html">
```
method는 get과 post방식이 있다.
post는 백엔드 즉 서버에 데이터를 보내는 방식
get은 보안에 취약하여 username이나 password를 보내면 안된다.  url에 포함되어도 상관없는, 보안에 신경쓰지 않아도 되는 데이터를 전송할 때 쓰인다.
___
### border-box
box-sizing : border-box
padding을 준만큼 박스사이즈를 줄이는 코드
![border-box](https://webisfree.com/static/uploads/2016/0a80_border-box.jpg)
___
### 한줄 코드로 여러줄의 중복코드 쉽게작성하기
```html
nav.classname>ul.classname__list>li.classname__btn*4>a.classname__link
```
결과
```html
<nav  class="classname">
	<ul  class="classname__list">
		<li  class="classname__btn">
			<a  href=""  class="classname__link"></a>
		</li>
		<li  class="classname__btn">
			<a  href=""  class="classname__link"></a>
		</li>
		<li  class="classname__btn">
			<a  href=""  class="classname__link"></a>
		</li>
		<li  class="classname__btn">
			<a  href=""  class="classname__link"></a>
		</li>
	</ul>
</nav>
```
___
### 앵커로 이동하는 ID
```html
<input id="idName"/>
<a  href="#idName"></a>
```
class는 적용 안되고 id만 적용된다.
위 코드처럼 하면 앵커를 누를시 앵커의 주소에 있는 id를 가진 태그로 바로 이동한다. 위의 경우 input이 바로 활성화된다.
___
### iframe
iframe이란 inline frame의 줄인말이다. iframe 요소를 이용하면 웹 페이지 안에 어떠한 제한 없이 또 다른 하나의 웹 페이지를 삽입할 수 있다.
예시)
```html
<iframe  src="https://image.ytn.co.kr/general/jpg/2019/1001/201910012341223645.jpg"  width="100%"  height="300px"  ></iframe>
<iframe  src="https://www.pdjournal.com/news/photo/201912/70786_70989_4229.jpg"  width="100%"  height="300px"></iframe>
```
결과) 위 코드와는 별개의 사진이나 아래 사진처럼 웹사이트안에 또다른 웹사이트가 만들어진다.
[![iframe](https://www.itopening.com/wp-content/uploads/2019/07/HTML-iframe-4.png)](https://www.itopening.com/667/)
___

## z-index

z-index는 css에서 포토샵의 layer기능을 한다.

```css
#chat  .status-bar  {
	background-color:  var(--chat-bgcolor);
	z-index:  2;
}
#chat  .alt-header  {
	background-color:  var(--chat-bgcolor);
	z-index:  1;
}
```

z-index의 default는 0이며 1부터 숫자가 올라갈 수록 상위 layer이 된다. 위 코드의 경우 .status-bar가 alt-header보다 상위에 위치하여 alt-header가 status-bar에 가려진다.

___
### border-radius 따로따로 지정하기
`border-top-left-radius:  0px;`
위처럼 상하, 좌우 순서대로 지정한 후 원하는 값을 입력한다.
___
두가지 element의 방향바꾸기

html코드를 수정하지 않고 두 element의 좌우 순서를 바꾸고 싶다면?
방법 1)
```css
.message-me  .message-row__bubble  {
	order:  1;
}
.message-me  .message-row__time  {
	order:  0;
}
```
위와 같이 order을 통해 직접 순서를 지정할 수 있다.
가장 빠른 순서는 0이다.
방법2)
```css
.message-me  .message-row__send  {
	flex-direction:  row-reverse;
}
```
flex할 때 배웠지만 flex-direction에 reverse를 사용하면 순서를 거꾸로 뒤집을 수 있다.
___
### will change

그래픽 카드를 이용하여 애니메이션을 가속
```css
.open-post__column:last-child  i:hover  {
will-change: transform;
animation: heart-bounce 1s  ease-in-out  infinite;
}
```
### 한개의 form에서 여러개의 submit을 쓰고싶을 때
submit에 attr로 formation을 준다,
formation="원하는 경로 주소"
```html
<input  type="submit"  value="Log in"  formaction="friends.html"  />
<input  type="submit"  value="Sign Up"  formaction="sign-up.html"  />
```
### css 단어, 글자, 문장 사이간격 조절
attr만 소개
글자간격 :  `letter-spacing`
단어간격 : `word-spacing`
줄간격 :  `line-height:  20px;`
___
### git branch
![git branch](https://blog.kakaocdn.net/dn/cRPkVU/btquUBRb7GK/bGy8lytovCtjsoP9SZKTJ0/img.jpg)
원본인 master에서 특정 commit을 기준으로 다른 버전의 작업물을 만드는 것을 branch라고 한다. branch=나뭇가지
따라서 시작점이 되는 commit이전의 commit들을 공통으로 가지고 그 이후부터는 서로 조금씩 코드와 결과물이 달리지게 된다. 코드를 저장을 하면  git desktop에서 change에 기록이 되는데 change말고 반드시 commit을 만들어야 제대로 branch에 저장을 할 수있다.
