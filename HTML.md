## HTML

* HTML5 문서는 반드시 <!DOCTYPE html>으로 시작하여 문서 형식(document type)을 HTML5로 지정한다.
* 실제적인 HTML document은 2행부터 시작되는데 <html> 과 </html> 사이에 기술한다.
* <head> </head> 사이에는 document title, 외부파일의 참조, metadata의 설정 등이 위치하며 이 정보들은 브라우저에 표시되지 않는다.
* 웹브라우저에 출력되는 모든 요소는 <body> </body> 사이에 위치한다.



### HTML5의 기본 문법

#### 요소(Element)

HTML 요소는 시작 태그(start tag)와 종료 태그(end tag) 그리고 태그 사이에 위치한 content로 구성된다.

HTML document는 요소(Element)들의 집합으로 이루어진다.

태그는 대소문자를 구별하지 않으나 W3C: World Wide Web Consortium에서는 HTML4의 경우 소문자를 추천하고 있으므로 HTML5에서도 소문자를 사용하는 것이 일반적.

**요소의 중첩(Nested Element)**

요소는 중첩될 수 있다. 요소는 다른 요소를 포함할 수 있다. 이때 부자관계가 성립된다. 이러한 부자관계로 정보를 구조화하는 것이다. 부자 관계(중첩 관계)를 시각적으로 파악하기 쉽게 indent(들여쓰기)를 활용한다. 

***빈 요소 (Empty Element)***

content를 가질 수 없는 빈 요소(Empty element or Self-Closing element)라 한다. 아래와 같이 빈 요소는 content가 없으며 (필요가 없다) 어트리뷰트(Attribute)만을 가질 수 있다.

빈 요소 중 대표적인 요소는 아래와 같다.

* br
* hr
* img
* input
* link
* meta

***어트리뷰트(Attribute)***

어트리뷰트(속성)이란 요소의 성질, 특징을 정의하는 명세이다. 요소는 어트리뷰트를 가질 수 있으며 어트리뷰트는 요소에 추가적 정보(예를 들어 이미지 파일의 경로, 크기 등)를 제공한다. 어트리뷰터는 시작 태그에 위치해야 하며 이름과 값의 쌍을 이룬다. (e.g name="'value'")

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image-20180717151134062.tiff)

**글로벌 어트리뷰트(HTML Global Attribute)**

글로벌 어트리뷰트는 모든 HTML 요소가 공통으로 사용할 수 있는 어트리뷰트다. 몇몇 요소에는 효과가 적용되지 않을 수 있지만, 글로벌 어트리뷰트는 대체로 모든 요소에 사용될 수 있다.

| Attribute | Description                                                  |
| --------- | ------------------------------------------------------------ |
| id        | 유일한 식별자(id)를 요소에 지정한다. 중복 지정이 불가하다.   |
| class     | 스타일시트에 정의된 class를 요소에 지정. 중복 지정이 가능하다. |
| hidden    | css의 hidden과는 다르게 의미상으로도 브라우저에 노출되지 않게 된다. |
| lang      | 지정된 요소의 언어를 지정한다. 검색엔진의 크롤링 시 웹페이지의 언어를 인식할 수 있게 한다. |
| style     | 요소에 인라인 스타일을 지정한다.                             |
| tabindex  | 사용자가 키보드로 페이지를 내비게이션 시 이동 순서를 지정한다. |
| title     | 요소에 관한 제목을 지정한다.                                 |

**주석(Comments)**

주석(comment)는 주로 개발자에게 코드를 설명하기 위해 사용되며 브라우저는 주석을 화면에 표시하지 않는다. 

```HTML
<!--주석은 화면에 표시되지 않는다.-->
<p>Lorem ipsum dolor sit amet</p>
```



## 요소의 의미를 명확히 설명하는 시맨틱 요소(Semantic element)와 검색 엔진 ##

인덱스를 생성할 때 사용되는 정보는 검색 로봇이 수집한 정보인데 결국 웹사이트의 HTML 코드이다. HTML 코드 만으로 그 의미를 인지하여야 하는데 이때 시맨틱 요소(Semantic element)를 해석하게 된다.

HTML으로 작성된 문서는 컴퓨터가 해석할 수 있는 메타데이터와 사람이 사용하는 자연어 문장이 뒤섞여 있다. 아래 코드를 보면 1행과 2행은 브라우저에서 동일한 외형을 갖는다. 이는 h1 태그의 디폴트 스타일이 1행과 같기 때문이다.

```HTML
<font size="6"><b>Hello</b></font>
<h1>Hello</h1>
```

1행의 요소는 의미론적으로 어떤 의미도 가지고 있지 않다. 즉, 의도가 명확하지 않다. 개발자가 의도한 요소의 의미를 명확하게 나타내지 않고 다만 폰트 크기와 볼드체를 지정하는 메타데이터만을 브라우저에게 알리고 있다. 그러나 2행의 요소는 header(제목) 중 가장 상위 레벨이라는 의미를 내포하고 있어서 개발자가 의도한 요소의 의미가 명확히 드러나고 있다. 이것은 코드의 가독성을 높이고 유지보수를 쉽게한다.

**시맨틱 태그란 브라우저, 검색엔진, 개발자 모두에게 콘텐츠의 의미를 명확히 설명하는 역할을 한다.** 시맨틱 태그에 의해 컴퓨터가 HTML 요소의 의미를 보다 명확히 해석하고 그 데이터를 활용할 수 있는 시맨틱 웹이 실현될 수 있다.

**시맨틱 웹이란 웹에 존재하는 수많은 웹페이지들에 메타데이터(Metadata)를 부여하여, 기존에 잡다한 데이터 집합이었던 웹페이지를 '의미'와 '관련성'을 가지는 거대한 데이터베이스로 구축하고자 하는 발상이다.

non-semantic 요소

div, span 등이 있으며 이들 태그는 content에 대하여 어떤 설명도 하지 않는다.

semantic 요소

font, table, img 등이 있으면 이들 태그는 content의 의미를 명확히 설명한다.

| tag     | Description                                           |
| ------- | ----------------------------------------------------- |
| header  | 헤더를 의미한다.                                      |
| nav     | 내비게이션을 의미한다.                                |
| aside   | 사이드에 위치하는 공간을 의미한다.                    |
| section | 본문의 여러 내용(article)을 포함하는 공간을 의미한다. |
| article | 본문의 주내용이 들어가는 공간을 의미한다.             |
| footer  | 푸터를 의미한다.                                      |

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image-20180717154458071.tiff)



## 1.3 HTML5 Tag- Basic##

웹페이지의 기본을 구성하는 태그



1. 문서 형식 정의 tag

문서 형식 정의(Document Type Definition, DTD) 태그는 출력할 웹 페이지의 형식을 브라우저에 전달한다. 문서의 최상위에 위치해야 하며 대소문자를 구별하지 않는다.

2. html tag

html 태그는 모든 HTML 요소의 부모 요소이며 웹페이지에 단 하나만 존재한다. 즉, 모든 요소는 html 요소의 자식 요소이며 html 요소 내부에 기술해야 한다. 단 <!DOCTYPE>는 예외이다.

html은 글로벌 어트리뷰트를 지원한다. 특히 lang 어트리뷰트를 사용하는 경우가 많다. 다음은 한국어를 주언어로 사용하는 경우의 예이다.

```html
<html lang="ko>		
```

3. head tag

head 요소는 메타데이터를 포함하기 위한 요소이며 웹페이지에 단 하나만 존재한다. 메타데이터는 HTML 문서의 title, style, link, script에 대한 데이터로 화면에 표시되지 않는다.

head 요소에는 메타데이터 이외의 화면에 표시되는 일체의 요소를 포함시킬 수 없다.

3.1 title tag

title 요소는 문서의 제목을 정의한다. 정의된 제목은 브라우저의 탭에 표신된다.

3.2 style tag

style 요소에는 HTML 문서를 위한 style 정보를 정의한다.

3.3 link tag

link 요소에는 외부 리소스와의 연계 정보를 정의한다. 주로 HTML과 외부 CSS 파일을 연계에 사용된다.

3.4 script tag

script 요소에는 client-side JavaScript를 정의한다.

src 어트리뷰트를 사용하면 외부 JavaScript 파일을 로드할 수 있다.

```HTML
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <script src="main.js"></script>
  </head>
  <body>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
  </body>
</html>
```

3.5 meta tag

meta 요소는 description, keywords, author, 기타 메타데이터 정의에 사용된다. 메타데이터는 브라우저, 검색엔진(keywords) 등에 의해 사용된다. charset 어트리뷰트는 브라우저가 사용할 문자셋을 정의한다.

SEO(검색엔진 최적화)를 위해 검색엔진이 사용할 keywords를 정의한다.

```
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
```

웹페이지의 설명을 정의한다.

```
<meta name="description" content="Web tutorials on HTML and CSS">
```

웹페이지의 저자를 명기한다.

```
<meta name="author" content="John Doe">
```

웹페이지를 30초 마다 Refresh한다.

```
<meta http-equiv="refresh" content="30">
```



4. body tag

body tag는 HTML 문서의 내용을 나타내며 웹페이지에 단 하나만 존재한다. 메타데이터를 제외한 웹페이즈를 구성하는 대부분의 요소가 body 요소 내에 기술된다.



## 1.4 HTML5 Tag- Text  텍스트 관련 태그

#### 1.제목 (Headings) 태그

Heading 태그는 제목을 나타낼 때 사용하며 h1에서 h6까지의 태그가 있다. h1이 가장 중요한 제목을 의미하며 글자의 크기도 가장 크다. 시맨택 웹의 의미를 살려서 제목 이외에는 사용하지 않는 것이 좋다. 검색엔진은 제목 태그를 중요한 의미로 받아들일 가능성이 크다.

#### 2.글자 형태 (Text Formatting) 태그

2.1 b

bold체를 지정한다. 제목 태그와 같이 의미론적(Semantic) 중요성의 의미는 없다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <p>This text is normal.</p>
    <b>This text is bold.</b>
    <p style="font-weight: bold;">This text is bold.</p>
  </body>
</html>
```

2.2 strong

b tag와 동일하게 bold체를 지정한다. 하지만 의미론적(Semantic) 	중요성의 의미를 갖는다. 표현되는 외양은 b tag와 동일하지만 웹표준을 준수하고자 한다면 strong를 사용하는 것이 바람직하다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <p>This text is normal.</p>
    <strong>This text is strong.</strong>
  </body>
</html>
```

This text is normal.

**This text is strong.**



2.3 i

Italic체를 지정한다. 의미론적(Semantic) 중요성의 의미는 없다.

``` HTML
<!DOCTYPE html>
<html>
  <body>
    <p>This text is normal.</p>
    <i>This text is italic.</i>
    <p style="font-style: italic;">This text is italic.</i>
  </body>
</html>
```

2.4 em

emphasize(강조, 중요한) text를 지정한다. i tag와 동일하게 Italic체로 표현된다. 의미론적(Semantic) 중요성의 의미를 갖는다.

2.5 small

small text를 지정한다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <h2>HTML <small>Small</small> Formatting</h2>
  </body>
</html>
```

2.6 mark

highlighted text를 지정한다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <h2>HTML <mark>Marked</mark> Formatting</h2>
  </body>
</html>
```

2.7 del

deleted(removed) text를 지정한다.

2.8 ins

inserted (added) text를 지정한다.

2.9 sub/ sup

sub	태그는 subscripted(아래에 쓰인) text를 sup 태그는 superscripted(위에 쓰인) text를 지정한다.

```html
<!DOCTYPE html>
<html>
  <body>
    <p>This is <sub>subscripted</sub> text.</p>
    <p>This is <sup>superscripted</sup> text.</p>
  </body>
</html>
```



#### 3. 본문 태그

3.1 p

단락(Paragraph)을 지정한다.

3.2 br

br tag는 (강제)개행 (line break)을 지정한다. br tag는 빈 요소(empty element)로 종료태그가 없다.

HTML에서는 1개 이상의 연속된 공백(space)을 삽입하여도 1개의 공백으로 표시된다. 1개 이상의 연속된 줄바꿈(enter)도 1개의 공백으로 표시된다.

연속적 공백을 삽입하는 방법은 아래와 같다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <p>This is&nbsp; a para&nbsp; &nbsp; graph</p>
  </body>
</html>
```

This is a para  graph



3.3 pre

형식화된(preformatted) text를 지정한다. pre 태그 내의 content는 작성된 그대로 브라우저에 표시된다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <p>HTML은 1개 이상의 연속된 공백(space)과 1개 이상의 연속된 줄바꿈(enter)을 1개의 공백으로 표시한다.</p>
    <pre>
var myArray = [];
console.log(myArray.length); // 0

myArray[1000] = true;  // [ , , ... , , true ]

console.log(myArray.length); // 1001
console.log(myArray[0]);     // undefined
    </pre>
  </body>
</html>
```

3.4 hr

수평줄을 삽입한다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <h1>HTML</h1>
    <p>HTML is a language for describing web pages.</p>
    <hr>
    <h1>CSS</h1>
    <p>CSS defines how to display HTML elements.</p>
  </body>
</html>
```

3.5 q

짧은 인용문(quotation)을 지정한다. 브라우저는 인용부호(큰따옴표/ quotation marks)로 q 요소를 감싼다.

```HTML
<!DOCTYPE html>
<html>
  <body>
    <p>Browsers usually insert quotation marks around the q element.</p>
    <p>WWF's goal is to: <q>Build a future where people live in harmony with nature.</q></p>
  </body>
</html>
```

3.6 blockquoute

긴 인용문 블록을 지정한다. 브라우저는 blockquoute 요소를 들여쓰기한다. css를 이용하여 다양한 style을 적용할 수 있다.

```html
<!DOCTYPE html>
<html>
  <body>
    <p>Browsers usually indent blockquote elements.</p>
    <blockquote>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
    </blockquote>
  </body>
</html>
```



## 1.5 HTML5 Tag - Link  HTML의 핵심 개념인 Hyperlink

Hyper는 컴퓨터 용어로서 텍스트 등의 정보가 동일 선상에 있는 것이 아니라 다중으로 연결되어 있는 상태를 의미한다. 한 텍스트에서 다른 텍스트로 건너뛰어 읽을 수 있는 이 기능을 하이퍼링크(hyper link)라 한다.

HTML link는 hyperlink를 의미하며 a(anchor) tag가 그 역할을 담당한다.

#### 1. href 어트리뷰트

href 어트리뷰트는 이동하고자 하는 파일의 위치(경로)를 값으로 받는다. 경로(path)란 파일 시스템 상에서 특정 파일의 위치를 의미한다.

#### 1.1 디렉터리(Directory)

디렉터리 파일과 다른 디렉터리를 갖는 파일 시스템 내의 존재물로서 폴더라고도 불리운다.

**루트 디렉터리 **

파일 시스템 계층 구조 상의 최상위 디렉터리.

* Windows: C:\

**홈 디렉터리 **

시스템의 사용자에게 각각 할당된 개별 디렉터리이다.

* Windows: C:\Users\ {계정명}

**작업 디렉터리 **

작업 중인 파일의 위치한 디렉터리이다.

* ./

**부모 디렉터리**

작업 디렉터리의 부모 디렉토리이다.

* ../



#### 1.2 파일 경로(File path)

파일 경로는 파일 시스템에서 파일의 위치를 나타내는 방법이다. 경로에는 절대경로와 상대경로가 있다.

**절대경로(Absolute path)**

현재 작업 디렉터리와 관계없이 특정 파일의 절대적인 위치를 가리킨다. 루트 디렉터리를 기준으로 파일의 위치를 나타낸다.

- http://www.mysite.com/index.html
- /Users/leeungmo/Desktop/myImage.jpg
- C:\users\leeungmo\Desktop\myImage.jpg
- /index.html

**상대경로(Relative path)**

현재 작업 디렉터리를 기준으로 특정 파일의 상대적인 위치를 가리킨다.

- ./index.html
- ../dist/index.js
- ../../dist/index.js
- index.html
- html/index.html



href 어트리뷰트에 사용 가능한 값은 아래와 같다.

| Value               | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| 절대 URL            | 웹사이트 URL (href="http://www.example.com/default.html")    |
| 상대 URL            | 자신의 위치를 기준으로한 대상의 URL (href="html/default.html") |
| fragment identifier | 페이지 내의 특정 id를 갖는 요소에의 링크 (#href="#top")      |
| 매일                | mailto:                                                      |
| script              | href="javascript:alert("Hello");"                            |



#### 2. target 어트리뷰트

target 어트리뷰트는 링크를 클릭했을 때 윈도우를 어떻게 오픈할 지를 지정한다.

| Value  | Description                                                  |
| ------ | ------------------------------------------------------------ |
| _self  | 링크를 클릭했을 때 연결문서를 현재 윈도우에서 오픈한다.(기본값) |
| _blank | 링크를 클릭했을 때 연결문서를 새로운 윈도우나 탭에서 오픈한다. |

```html
<!DOCTYPE html>
<html>
  <body>
    <a href="http://www.google.com" target="_blank">Visit google.com!</a>
  </body>
</html>
```



## 1.6 HTML5 Tag- List & Table  목록(List)와 표(Table) 형식 표현을 위한 태그

#### 1. 목록(List)

#### 1.1 순서없는 목록 (Unordered List)

```
<!DOCTYPE html>
<html>
  <body>
    <h2>순서없는 목록 (Unordered List)</h2>
    <ul>
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ul>  
  </body>
</html>
```



#### 1.2 순서있는 목록 (Ordered List)

```
<!DOCTYPE html>
<html>
  <body>
    <h2>순서있는 목록 (Ordered List)</h2>
    <ol>
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ol>  
  </body>
</html>
```



type 어트리뷰트를 사용하여 순서를 나타내는 문자를 지정할 수 있다.

| Value | Description     |
| ----- | --------------- |
| "1"   | 숫자(기본값)    |
| "A"   | 대문자 알파벳   |
| "a"   | 소문자 알파벳   |
| "I"   | 대문자 로마숫자 |
| "i"   | 소문자 로마숫자 |

```HTML
<ol type="I">
  <li value="2">Coffee</li>
  <li value="4">Tea</li>
  <li>Milk</li>
</ol>
```

start 어트리뷰트로 리스트의 시작값을 지정할 수 있다.

reversed 어트리뷰트를 지정하면 리스트의 순서값을 역으로 표현한다.



#### 1.3 중첩 목록

목록 태키는 내비게이션 메뉴를 만들 때 자주 사용된다.



### 2. 테이블

표(table)를 만들 때 사용하는 태그이다. 과거에는 테이블 태그를 사용하여 레이아웃을 구성하기도 하였으나 모던 웹에서는 주로 공간 분할 태그인 div 태그를 사용하여 레이아웃을 구성한다. 

| tag   | Description                       |
| ----- | --------------------------------- |
| table | 표를 감싸는 태그                  |
| tr    | 표 내부의 행 (table row)          |
| th    | 행 내부의 제목 셀 (table heading) |
| td    | 행 내부의 일반 셀 (table data)    |

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image-20180717192449556.tiff)

| attribute | Description                                                  |
| --------- | ------------------------------------------------------------ |
| border    | 표 테두리 두께 지정. (CSS border property를 사용하는 것이 더 나은 방법이다.) |
| rowspan   | 해당 셀이 점유하는 행의 수 지정                              |
| colspan   | 해당 셀이 점유하는 열의 수 지정                              |

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      table, th, td {
        border: 1px solid black;
        border-collapse: collapse; 
      }
      th, td {
        padding: 15px;
      }
    </style>
  </head>
  <body>
    <h2>2개의 culumn을 span</h2>
    <table>
      <tr>
        <th>Name</th>
        <th colspan="2">Telephone</th>
      </tr>
      <tr>
        <td>Bill Gates</td>
        <td>555 77 854</td>
        <td>555 77 855</td>
      </tr>
    </table>

    <h2>2개의 row를 span</h2>
    <table>
      <tr>
        <th>Name:</th>
        <td>Bill Gates</td>
      </tr>
      <tr>
        <th rowspan="2">Telephone:</th>
        <td>555 77 854</td>
      </tr>
      <tr>
        <td>555 77 855</td>
      </tr>
    </table>
  </body>
</html>
```

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image-20180717194201028.tiff)



## 1.7 HTML5 Tag - Image & Multimedia  이미지의 표현과 동영상, 음악 등 멀티미디어를 지원하는 태그

#### 1. 이미지

웹페이지에 이미지를 삽입하는 경우, img tag를 사용한다.

| attribute | Description                                  |
| --------- | -------------------------------------------- |
| src       | 이미지 파일 경로                             |
| alt       | 이미지 파일이 없을 경우 표시되는 문장        |
| width     | 이미지의 너비 (CSS에서 지정하는 것이 일반적) |
| height    | 이미지의 높이 (CSS에서 지정하는 것이 일반적) |

```html
<!DOCTYPE html>
<html>
  <body>
    <img src="assets/images/doug.jpg" alt="Smiley face" width="100">
    <img src="assets/images/wrongname.gif" alt="이미지가 없습니다.">
  </body>
</html>
```

#### 2. 미디어

#### 2.1 audio

audio 태그는 HTML5에서 새롭게 추가된 태그이다. IE8 이하에서는 사용할 수 없다.

| attribute | Description                                                  |
| --------- | ------------------------------------------------------------ |
| src       | 음악 파일 경로                                               |
| preload   | 재생 전에 음악 파일을 모두 불러올 것인지 지정                |
| autoplay  | 음악 파일을 자동의 재생 개시할 것인지 지정                   |
| loop      | 음악을 반복할 것인지 지정                                    |
| controls  | 음악 재생 도구를 표시할 것인지 지정. 재생 도구의 외관은 브라우저마다 차이가 있다. |

웹브라우저 별로 지원하는 음악 파일 형식이 다르다. 파일 형식에 따라 재생되지 않는 브라우저가 존재한다는 뜻이다.

| Browser           | MP3      | Wav  | Ogg  |
| ----------------- | -------- | ---- | ---- |
| Internet Explorer | YES      | NO   | NO   |
| Chrome            | YES      | YES  | YES  |
| Firefox           | YES(24~) | YES  | YES  |
| Safari            | YES      | YES  | NO   |
| Opera             | YES(25~) | YES  | YES  |

source 태그를 사용하여 파일 형식의 차이 문제를 해결 할 수 있다. type 어트리뷰트는 생략 가능하다.

#### 2.2 비디오

video 태그는 HTML5에서 새롭게 추가된 태그이다. IE8 이하에서는 사용할 수 없다.

| attribute | Description                                                  |
| --------- | ------------------------------------------------------------ |
| src       | 동영상 파일 경로                                             |
| poster    | 동영상 준비 중에 표시될 이미지 파일 경로                     |
| preload   | 재생 전에 동영상 파일을 모두 불러올 것인지 지정              |
| autoplay  | 동영상 파일을 자동의 재생 개시할 것인지 지정                 |
| loop      | 동영상을 반복할 것인지 지정                                  |
| controls  | 동영상 재생 도구를 표시할 것인지 지정. 재생 도구의 외관은 브라우저마다 차이가 있다. |
| width     | 동영상의 너비를 지정                                         |
| height    | 동영상의 높이를 지정                                         |

audio 태그와 마찬가지로 파일 형식의 차이 문제가 발생할 수 있다. source 태그를 사용하여 형식 차이 문제를 해결한다. type 어트리뷰트는 생략 가능하다.

| Browser           | MP4      | WebM | Ogv  |
| ----------------- | -------- | ---- | ---- |
| Internet Explorer | YES      | NO   | NO   |
| Chrome            | YES      | YES  | YES  |
| Firefox           | YES(21~) | YES  | YES  |
| Safari            | YES      | NO   | NO   |
| Opera             | YES(25~) | YES  | YES` |

```html
<!DOCTYPE html>
<html>
  <body>
    <video width="640" height="360" controls>
      <source src="assets/video/Wildlife.mp4" type="video/mp4">
      <source src="assets/video/Wildlife.webm" type="video/webm">
    </video>
  </body>
</html>
```



## 1.8 HTML5 Tag-Forms  사용자와의 커뮤니케이션을 위한 태그

#### 1. form

form 태그는 사용자가 입력한 데이터를 수집하기 위해 사용되며 input, textarea, button, select, checkbox, radio button, submit button 등의 입력 양식 태그를 포함할 수 있다.

| attribute | Value    | Description                              |
| --------- | -------- | ---------------------------------------- |
| action    | URL      | 입력 데이터(form data)가 전송될 URL 지저 |
| method    | get/post | 입력 데이터(form data)전달 방식 지정     |

GET과 POST는 HTTP 프로토콜을 이용해서 사용자 입력 데이터를 서버에 전달하는 방식을 나타내며 HTTP request method라 한다.

GET

* GET 방식은 전송 URL에 입력 데이터를 쿼리스트링으로 보내는 방식이다.
* ex) http://jsonplaceholder.typicode.com/posts?userId=1&id=1
* 전송 URL 바로 뒤에 "?"를 통해 데이터의 시작을 알려주고, key-value 형태의 데이터를 추가한다. 1개 이상의 전송 데이터는 '&'로 구분한다.
* URL에 전송 데이터가 모두 노출되기 때문에 보안에 문제가 있으며 전송할 수 있는 데이터의 한계가 있다. (최대 255자)
* REST API에서 GET 메소드는 모든 또는 특정 리소스의 조회를 요청한다.

POST

* POST 방식은 Request Body에 담아 보내는 방식이다.
* ex) http://jsonplaceholder.typicode.com/posts
* URL에 전송 데이터가 모두 노출되지 않지만 GET에 비해 속도가 느리다.
* REST API에서 POST 메소드는 특정 리소스의 생성을 요청한다.

```html
<!DOCTYPE html>
<html>
  <body>
    <form action="http://jsonplaceholder.typicode.com/users" method="get">
      ID: <input type="text" name="id" value="1"><br>
      username: <input type="text" name="username" value="Bret"><br>
      <input type="submit" value="Submit">
    </form>
  </body>
</html>	
```

submit button이 클릭되면 input 태그에 입력된 데이터가 form 태그의 method 어트리뷰트에 지정된 방식으로 action 어트리뷰트에 지정된 서버측의 처리 로직에 전달된다.



#### 2.input

input 태그는 form 태그 중에서 가장 중요한 태그로 사용자로부터 데이터를 입력받기 위해 사용된다.

input 태그는 다양한 종류가 있는데 type 어트리뷰트에 의해. 구분된다. form 태그 내에 존재하여야 입력 데이터를 전송할 수 있으나 ajax를 사용할 시에는 form 태그 내에 존재하지 않아도 도니다.

서버에 전송되는 데이터는 name 어트리뷰트를 키로, value 어트리뷰트를 값으로 하여 key=value의 형태로 전송된다.

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image-20180717203721186.tiff)



```html
<!DOCTYPE html>
<html>
  <body>
    <h3>button</h3>
    <input type="button" value="Click me" onclick="alert('Hello world!')">
    <hr>

    <h3>checkbox</h3>
    <input type="checkbox" name="fruit1" value="apple" checked> 사과<br>
    <input type="checkbox" name="fruit2" value="grape"> 포도<br>
    <input type="checkbox" name="fruit3" value="peach"> 복숭아<br>
    <hr>

    <h3>color</h3>
    <input type="color" name="mycolor">
    <hr>

    <h3>date</h3>
    <input type="date" name="birthday">
    <hr>

    <h3>datetime</h3>
    <input type="datetime" name="birthdaytime">
    <hr>

    <h3>datetime-local</h3>
    <input type="datetime-local" name="birthdaytime">
    <hr>

    <h3>email</h3>
    <input type="email" name="useremail">
    <hr>

    <h3>file</h3>
    <input type="file" name="myfile">
    <hr>

    <h3>hidden</h3>
    <input type="hidden" name="country" value="Norway">
    hidden filed는 사용자에 표시되지 않는다.
    <hr>

    <h3>image</h3>
    <input type="image" src="img/img_submit.gif" alt="Submit" width="48" height="48">
    <hr>

    <h3>month</h3>
    <input type="month" name="birthdaymonth">
    <hr>

    <h3>number</h3>
    <input type="number" name="quantity" min="2" max="10" step="2" value="2">
    <hr>

    <h3>password</h3>
    <input type="password" name="pwd">
    <hr>

    <h3>radio</h3>
    <input type="radio" name="gender" value="male" checked> 남자<br>
    <input type="radio" name="gender" value="female"> 여자<br>
    <hr>

    <h3>range</h3>
    <input type="range" name="points" min="0" max="10" step="1" value="5">
    <hr>

    <h3>reset</h3>
    <input type="reset">
    <hr>

    <h3>search</h3>
    <input type="search" name="googlesearch">
    <hr>

    <h3>submit</h3>
    <input type="submit" value="Submit">
    <hr>

    <h3>tel</h3>
    <input type="tel" name="mytel">
    <hr>

    <h3>text</h3>
    <input type="text" name="myname">
    <hr>

    <h3>time</h3>
    <input type="time" name="mytime">
    <hr>

    <h3>url</h3>
    <input type="url" name="myurl">
    <hr>

    <h3>week</h3>
    <input type="week" name="week_year">
  </body>
</html>
```



#### 3. select

복수개의 리스트에서 복수개의 아이템을 선택할 때 사용한다. 함께 사용할 수 있는 태그는 다음과 같다. 서버에 전송되는 데이터는 select 요소의 name 어트리뷰트를 키로, option 요소의 value 어트리뷰트를 값으로하여 key=value의 형태로 전송된다.

| tag      | Description          |
| -------- | -------------------- |
| select   | select form 생성     |
| option   | option 생성          |
| optgroup | option을 그룹화한다. |

```html
<!DOCTYPE html>
<html>
  <body>
    <select name="cars1">
      <option value="volvo" selected>Volvo</option>
      <option value="saab" disabled>Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi">Audi</option>
    </select>

    <select name="cars2" size="4" multiple>
      <option value="volvo">Volvo</option>
      <option value="saab">Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi" selected>Audi</option>
    </select>

    <select name="cars3">
      <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
      </optgroup>
      <optgroup label="German Cars" disabled>
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
      </optgroup>
    </select>
  </body>
</html>
```

#### 4. textarea

textarea 태그는 여러 줄의 글자를 입력할 때 사용한다.

```html
<!DOCTYPE html>
<html>
  <body>
    <select name="cars1">
      <option value="volvo" selected>Volvo</option>
      <option value="saab" disabled>Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi">Audi</option>
    </select>

    <select name="cars2" size="4" multiple>
      <option value="volvo">Volvo</option>
      <option value="saab">Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi" selected>Audi</option>
    </select>

    <select name="cars3">
      <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
      </optgroup>
      <optgroup label="German Cars" disabled>
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
      </optgroup>
    </select>
  </body>
</html>
```



#### 5.button

button 태그는 클릭할 수 있는 버튼을 생성한다. <input type ="button">과 유사하지만 Input 태그는 빈 태그인 반면 button 태그는 그렇지 않다. 따라서 button 요소에는 텍스트나 이미지 같은 콘텐츠를 사용할 수 있다.

type 어트리뷰트는 반드시 지정하는 것이 바람직하며 어트리뷰트값으로 button, reset, submit를 지정할 수 있다.

```
<!DOCTYPE html>
<html>
  <body>
    <button type="button" onclick="alert('Hello World!')">Click Me!</button>

    <input type="button" value="Click Me!" onclick="alert('Hello world!')">
  </body>
</html>
```

button 태그는 어트리뷰트만을 받아들이는 input 태그와 달리 콘텐츠로 문자열은 물론 HTML 요소를 받을 수도 있다는 장점이 있다. 주의할 것은 IE의 경우, submit되는 값이 다룰 수 있는 것이다. 



#### 6. filedset / legend

fieldset 태그는 관련된 입력 양식들을 그룹화할 때 사용한다. legend 태그는 fieldset 태그 내에서 사용되야 하며 그룹화된 filedset의 제목을 정의한다.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
  </head>
  <body>
      <fieldset>
        <legend>Login</legend>
        Username <input type="text" name="username">
        Password <input type="text" name="password">
      </fieldset>
  </body>
</html>
```

## 1.9 HTML5 Tag - Structure 웹페이지의 레이아웃을 구성하기 위해 공간을 분할하는 태그

웹페이지의 레이아웃을 구성하기 위해서 공간을 분할할 필요가 있다.

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image-20180717210012655.tiff)

공간을 분할할 수 있는 태그는 div, span, table 등이 있는데, 과거에는 table 태그를 사용하여 레이아웃을 구성하기도 하였으나 모던 웹에서는 주로 div를 사용하여 레이아웃을 구성한다.

그런데 div 태그는 의미론적으로 어떠한 의미도 가지고 있지 않기 때문에 아래와 같이 HTML5에서 새롭게 추가된 시맨틱 태그를 사용하는 것이 더 나은 방법이나 IE에서 작동하지 않기 때문에 주의가 필요하다.

| tag     | Description                                           |
| ------- | ----------------------------------------------------- |
| header  | 헤더를 의미한다.                                      |
| nav     | 내비게이션을 의미한다.                                |
| aside   | 사이드에 위치하는 공간을 의미한다.                    |
| section | 본문의 여러 내용(article)을 포함하는 공간을 의미한다. |
| article | 본문의 주내용이 들어가는 공간을 의미한다.             |
| footer  | 푸터를 의미한다.                                      |

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image-20180717210317682.tiff)

이와 같은 공간 분할 태그는 일반적으로 다른 요소를 포함하는 컨테이너 역할을 하게 된다. 

div와 span의 차이는 block 레벨 요소와 inline 레벨 요소를 이해하여야 한다.

이에 대한 자세한 내용은 display 프로퍼티를 참조하기 바란다.