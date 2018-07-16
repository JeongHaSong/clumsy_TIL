## 2.6 CSS3 Background "HTML 요소의 배경으로 이미지 또는 색상을 정의"

1. background-image 프로퍼티

요소에 배경 이미지를 지정

2. background-repaeat 프로퍼티

배경 이미지의 반복을 지정. 수직, 수평 또는 수직과 수평 모두의 반복을 지정할 수 있다. 

설정된 이미지의 크기가 화면보다 작으면 자동으로 이미지가 반복 출력되어 화면을 채우게 된다.

이것은 background-repeat 프로퍼티의 기본값이 repeat이기 때문.

repeat-x : x축으로만 배경 이미지를 반복

repeat-y: y축으로만 배경 이미지를 반복

! 반복 출력을 멈추고 싶은 경우, background-repeat 프로퍼티값에 no-repat를 설정.

! background-image에 복수개의 이미지를 설정할 경우, 먼저 설정된 이미지가 전면에 출력.

3. background-size 프로퍼티

배경 이미지의 사이즈를 지정. 배경 이미지의 고유 비율을 유지하기 때문에 설정에 따라 이미지의 일부가 보이지 않을 수 있다. 프로퍼티 값은 **px, %, cover, contain** 등을 사용한다. 

배경이미지의 width, height를 모두 설정할 수 있다. 이때 첫번째 값은 width, 두번째 값은 height를 의미한다. **하나의 값만을 지정한 경우, 지정한 값은 width를 의미하게 되며 height는 auto로 지정된다.**

**px값 지정**

배경이미지가 크기가 지정된 px값 그대로 설정된다. 첫번째 값은 width, 두번째 값은 height를 의미한다.

```CSS
.bg{
    background-size: 700px 500px;
}
```

**%값 지정**

배경이미지 크기가 지정된 %값에 비례하여 설정된다. 첫번째 값은 width, 두번째 값은 height를 의미한다. 화면을 줄이거나 늘리면 배경이미지의 크기도 따라서 변경되어 찌그러지는 현상이 나타난다.

**cover 지정**

배경이미지 크기 비율을 유지한 상태에서 부모 요소의 width, height 중 큰값에 배경이미지를 맞춘다. 따라서 이미지의 일부가 보이지 않을 수 있다.

**contain 지정**

배경이미지의 크기 비율을 유지한 상태에서 부모 요소의 영역에 배경이미지가 보이지 않는 부분없이 전체가 들어갈 수 있도록 이미지 스케일을 조정한다. width, height의 프로퍼티값은 공백으로 구분하여야 한다. 프로퍼티값을 쉼표로 구분하면 다른 배경이미지의 너비를 지정하는 것으로 인식되기 때문에 주의가 필요하다.

4. background-attachment 프로퍼티

일반적으로 화면을 스크롤하면 배경 이미지도 함께 스크롤된다. 화면이 스크롤되더라도 배경이미지는 스크롤되지 않고 고정되어 있게 하려면 background-attachment 프로퍼티에 fixed 키워드를 지정한다.

5. background-position 프로퍼티

일반적으로 background-image는 좌상단부터 이미지를 출력한다. 이때 background-position 프로퍼티를 사용하면 이미지의 좌표(xpos, ypos)를 지정 할 수 있다.

기본값은 background-position: 0%, 0%;로 배경이미지는 우측 상단에 위치하게 된다.

```css
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      margin: 0;
    }
    div {
      background-image: url("http://poiemaweb.com/img/bg/dot.png");
      background-color: #FFEE99;
      background-repeat: no-repeat;
      width: 32vw;
      height: 200px;
      margin-bottom: 2vw;
      float: left;
    }
    div:not(:nth-of-type(3n+1)) {
      margin-left: 2vw;
    }
    .example1 {
      background-position: top;
    }
    .example2 {
      background-position: bottom;
    }
    .example3 {
      background-position: center;
    }
    .example4 {
      background-position: left;
    }
    .example5 {
      background-position: right;
    }
    .example6 {
      /* <percentage> values */
      background-position: 25% 75%;
    }
    .example7 {
      /*
        <length> values
        xpos ypos     
      */
      background-position: 10px 20px;
    }
    .example8 {
      background-image: url("http://poiemaweb.com/img/bg/dot.png"), url("http://poiemaweb.com/img/bg/dot.png");
      background-position: 0px 0px, center;
    }
  </style>
</head>

<body>
  <div>default(0% 0%)</div>
  <div class="example1">top</div>
  <div class="example2">bottom</div>
  <div class="example3">center</div>
  <div class="example4">left</div>
  <div class="example5">right</div>
  <div class="example6">25% 75%</div>
  <div class="example7">10px 20px</div>
  <div class="example8">0px 0px, center</div>
</body>
</html>
```

6. background-color 프로퍼티

background-color 프로퍼티는 요소의 배경 색상을 지정한다. 색상값 또는 transparent 키워드를 지정할 수 있다.

7. background Shorthand

background-color, background-image, background-repeat, background-position를 한번에 정의하기 위한 Shorthand Syntax이다.

``` css
// order
background: color || image || repeat || attachment || position

<!DOCTYPE html>
<html>
<head>
  <style>
    div {
      /* background: color || image || repeat || attachment || position */
      background: #FFEE99 url("http://poiemaweb.com/img/bg/dot.png") no-repeat center;
      width: 50vw;
      height: 300px;
    }
  </style>
</head>
<body>
  <div></div>
</body>
</html>
```



## 2.7 CSS3 Font & Text  "폰트 및 텍스트에 관련된 프로퍼티"

1. font-size 프로퍼티

텍스트의 크기를 정의한다.

2. font-family 프로퍼티

폰트를 지정한다. 컴퓨터에 해당 폰트가 설치되어 있지 않으면 적용되지 않는다.

* font-family

폰트는 동시에 여러 개를 지정이 가능. 첫번째 지정한 폰트가 클라이언트 컴퓨터에 설치되어 있지 않은 경우, 다음에 지정된 폰트를 적용한다. 따라서 마지막에 지정하는 폰트는 대부분의 OS에 기본적으로 설치되어 있는 generic-family폰트 (Serif, Sans-serif, Mono space)를 지정하는 것이 일반적.

! 폰트명은 따옴표로 감싸주며 폰트명이 한단어인 경우는 따옴표로 감싸주지 않아도 된다.

3. font-style/ font-weight 프로퍼티

font-style 프로퍼티는 이탤릭체의 지정, font-weight 프로퍼티는 폰트 굵기 지정에 사용된다.

4. font Shorthand

```css
font: font-style(optional) font-variant(optional) font-weight(optional) font-size(mandatory) line-height(optional) font-family(mandatory)

/* size | family */
font: 2em "Open Sans", serif;

/* style | size | family */
font: italic 2em "Open Sans", sans-serif;

/* style | variant | weight | size/line-height | family */
font: italic small-caps bolder 16px/1.2 monospace;

/* style | variant | weight | size/line-height | family */
/* font-variant: small-caps; 소문자를 대문자로 만든다. 단 크기는 일반 대문자에 비해 더 작다.*/
font: italic small-caps bolder 16px/3 cursive;
```



5. line-height 프로퍼티

텍스트의 높이를 지정한다. 텍스트의 수직 정렬에도 응용되어 사용된다.

수직 중앙 정렬을 위해서는 a 요소의 line-height 값과 a 요소를 감싸는 div 요소의 height 값을 일치시킨다.

```css
<!DOCTYPE html>
<html>
<head>
  <style>
    .button {
      width: 150px;
      height: 70px;
      background-color: #FF6A00;
      border-radius: 30px;
      box-shadow: 5px 5px 5px #A9A9A9;
    }
    .button > a {
      display: block;
      font: italic bold 2em/70px Arial, Helvetica, sans-serif;
      text-decoration: none;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="button">
    <a href="#">Click</a>
  </div>
</body>
</html>
```

6. letter-spacing 프로퍼티

글자 사이의 간격을 지정한다.

7. text-align 프로퍼티

텍스트의 수평 정렬을 정의한다.

8. text-decoration 프로퍼티

text-decoration 프로퍼티를 사용하여 링크 underline을 제거할 수 있다. 또는 텍스트에 underline, overline, line-through를 추가할 수도 있다.

9. white-space 프로퍼티

white space는 공백(space), 들여쓰기(tab), 줄바꿈(line break)을 의미한다. html은 기본적으로 연속된 공백, 들여쓰기는 1번만 실행되며 줄바꿈은 무시된다. 또한 텍스트는 부모 가로 영역을 벗어나지 않고 자동 줄바꿈(wrap)된다. white-space 프로퍼티는 이러한 기본 동작을 제어하기 위한 프로퍼티이다.

| 프로퍼티값 | line break | space/tab | wrapping(자동줄바꿈) |
| ---------- | ---------- | --------- | -------------------- |
| normal     | 무시       | 1번만     | O                    |
| nowrap     | 무시       | 1번만     | X                    |
| pre        | 반영       | 반영      | X                    |
| pre-wrap   | 반영       | 반영      | O                    |
| pre-line   | 반영       | 1번만     | O                    |

10. text-overflow 프로퍼티

부모 영역을 벗어난 wrapping(자동줄바꿈)이 되지 않은 텍스트의 처리 방법을 정의한다. 이 프로퍼티를 사용하기 위해서는 아래의 조건이 필요하다.

* overflow 프로퍼티에 반드시 "visible"이외의 값이 지정되어 있어야 한다.
* width 프로퍼티가 지정되어 있어야 한다. 이를 위해 필요할 경우 block 레벨 요소로 변경하여야 한다.
* 자동 줄바꿈을 방지하려면 white-space 프로퍼티를 nowrap으로 설정한다.

text-overflow 프로퍼티에 설정할 수 있는 프로퍼티값은 아래와 같다.

| 프로퍼티값 | Description                                                  |
| ---------- | ------------------------------------------------------------ |
| clip       | 영역을 벗어난 부분을 표시하지 않는다. (기본갑)               |
| ellipsis   | 영역을 벗어난 부분을 잘라내어 보이지 않게 하고 말줄임표(...)를 표시한다. |
| <string>   | 값으로 지정한 임의의 문자열을 출력한다. FIrefox(9.0~)만 지원하는 기능. |

11. word-wrap 프로퍼티

한 단어의 길이가 길어서 부모 영역을 벗어난 텍스트의 처리 방법을 정의한다. link 등을 표기할 때 그 길이가 매우 길어지는데 이 프로퍼티를 사용하지 않으면 부모 영역을 넘어가게 된다.

12. word-break 프로퍼티

한 단어의 길이가 길어서 부모 영역을 벗어난 텍스트의 처리 방법을 정의한다.

word-wrap 프로퍼티는 단어를 어느 정도는 고려하여 개행하지만(.,-등을 고려한다.) word-break: break-all; 는 단어를 고려하지 않고 부모 영역에 맞추어 강제 개행한다.