

**Useful Methods**

- Manipulation
  - addClass / removeclass
  - html/text
  - append/appendTo
  - prepend/prependTo
  - remove/ empty 
  - val
- Event
  - on/off
- Effect
  -  show /hide

제이쿼리를 사용하여 스타일 추가 및 제거하기 위해 클래스(class) 속성을 선택자로 사용. 그 외에 동적인 스크립트 및 액션 등은 자바스크립트의 ID 값을 많이 사용. 이렇게 **클래스명을 추가하거나 제거하면 간단하게 원하는 스타일을 추가 또는 제거하는 것이 가능.** 물론 해당하는 class에는 스타일이 css에 선언되어야 한다.

보통 클래스에 스타일을 정해두고 이 클래스를 추가하거나 제거하는 방법이 사용됨.

**addClass()**

addClass() 속성을 사용하면 특정 요소에 새로운 클래스를 추가할 수 있다. 이미 가지고 있는 클래스는 더 이상 추가되지 않는다.

```html
<style>
 .red{color:red;}
</style>

<span>Test addClass</span>
```

```html
// span 태그가 존재할 경우 여기에 red 클래스를 주어 폰트색을 변경하는 예제를 만드는 법

$('span').addClass('red');
```

```html
// Add the class "selected" to the matched elements.
<!doctype html>
<html lang = "en">
<head>
 <meta charset = "utf-8">
 <title>addClass demo</title>
 <style>
 p {
     margin : 8px;
     font-size : 16px;
 }
 .selected {
     color: blue;
 }
 .highlight {
     background: yellow;
 }
 </style>
 <script src = "https://code.jquery.com/jquery-1.10.2.js"></script>
 </head>
 <body>
 
 <p>Hello</p>
 <p>and</p>
 <p>Goodbye</p>
 
 <script>
 $("p").last().addClass("selected");
 </script>
 
 </body>
 </html>

// Hello
   and
   Goodbye // 파란색
```

```html
// Add the classes 'selected' and 'hightlight' to the matched elements.
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>addClass demo</title>
  <style>
      p {
          margin : 8px;
          font-size : 16px;
      }
      .selected {
          color : red;
      }
      .highlight {
          background : yellow;
      }
    </style>
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>
 
<p>Hello</p>
<p>and</p>
<p>Goodbye</p>
    
    <script>
    $("p:last").addClass("selected highlight");
    </script>
    
    </body>
</html>

Hello
and
Goodbye // 빨간 글씨, 노란 배경
```



**removeClass()**

$(Element).removeClass('클래스명');

클래스 속성이 가지고 있는 선택한 클래스명을 삭제. 이 메소드는 선택된 클래스 모두를 제거하며 만약 해당 클래스가 없는 경우 아무런 변화가 없다.

Description : Remove a single class, multiple classes, or all classes from each element in the set of matched elements.

More than one class may be removed at a time, separated by a space, from the set of matched elements, like so :

```html
$("p").removeClass("myClass yourClass")
```

This method is often used with .addClass() to switch elements' classes from one to another, like so:

```html
$("p").removeClass("myClass no Class").addClass("yourClass")
```

Here, the myClass and noClass classes are removed from all paragraphs, while yourClass is added.

To replace all existing classes with another class, we can use .attr("class", "newClass") instead.

```html
<body>
 <span class = "test">Test removeClass</span>
</body>
 
 <script type = "text/javascript">
 $('span').removeClass('test');
 </script>
```

```html
위 코드를 실행할 경우 아래처럼 class가 제거되어 나타난다.
<body>
 <span class> Test removeClass </span>
</body>
```

Examples:

```html
// Remove the class 'blue' from the matched elements.
<!doctype html>
<html lang = "en">
    <head>
        <meta charset = "utf-8">
        <title>removeClass demo</title>
        <style>
            p {
                margin : 4px;
                font-size : 16px;
                font-weight : bolder;
            }
            .blue {
                color: blue;
            }
            .highlight {
                background: yellow;
            }
            
        </style>
        <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    </head>
    <body>
        
        <p class = "blue under">Hello</p>
        <p class = "blue under highlight">and</p>
        <p class = "blue under">then</p>
        <p class = "blue under">Goodbye</p>
    <script>
        $("p:even").removeClass("blue");
        </script>  
    </body>
</html>

//Hello   // 파란색 클래쓰 제거
  and
  then    // 파란색 클래쓰 제거
  Goodbye
```

```html
//Remove the class 'blue' and 'under' from the matched elements.
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>removeClass demo</title>
  <style>
  p {
    margin: 4px;
    font-size: 16px;
    font-weight: bolder;
  }
  .blue {
    color: blue;
  }
  .under {
    text-decoration: underline;
  }
  .highlight {
    background: yellow;
  }
  </style>
  <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>
    
    <p class = "blue under">
        Hello
    </p>
    <p class = "blue under highlight">
        and
    </p>
    <p class = "blue under">
        then
    </p>
    <p class = "blue under">
        Goodbye
    </p>
    <script>
    $("p:odd").removeClass("blue under");
    </script>
```

#### text() 와 html() 함수

어떤 p태그 안에 내용이 hello가 있다면 text()를 사용해서 konnichiha로 변경할 수 있다. 

```html
// HTML
<p class = "change_greeting">hello</p>

// jQuery
$('.change_greeting').text('konnichiha');
```

```html
<!doctype html>
<html>
<head>
<meta charset="utf-8" />
<title>EVERDEVEL :: 제이쿼리 강좌</title>
<script type="text/javascript"
src="http://code.jquery.com/jquery-2.1.0.min.js">
</script>
<script type="text/javascript">
$(function(){
  $('.change_greeting').text('konnichiha');
});
</script>
</head>
<body>
    <p class="change_greeting">hello</p>
</body>
</html>

이렇게 되면 change_greeting가 감싸고 있는 텍스트는 konnichiha로 변경된다.
```

반대로 아무것도 쓰지 않는다면 해당하는 요소가 감싸는 텍스트를 가지고 오는 기능도 있다. //

```html
//다음 예제는 클래스 hello감싸는 텍스트hello를 jquery의 text()가 값을 가져와서 alert창으로 띄워주는 소스

HTML
<p clas="hello">hello</p>

jQuery
var i = $('.hello').text();
alert(i);	
```

```html
<!doctype html>
<html>
<head>
<meta charset="utf-8" />
<title>EVERDEVEL :: 제이쿼리 강좌</title>
<script type="text/javascript"
src="http://code.jquery.com/jquery-2.1.0.min.js">
</script>
<script type="text/javascript">
    $(function(){
        var i = $('.hello').text(); 
        alert(i);
    });
</script>
</head>
<body>
<p class="hello">hello</p>
</body>
</html>

// hello 가 alert 된다.
```

**html()**

text()은 텍스트만 불러오지만 html()은 html태그도 불러 옵니다.

```html
$.('class_Name').html('hello');
```

위와 같이 괄호 안에 태그를 사용할 수 있습니다.

위의 text()예제를 html로 변경해서 사용. hello를 볼드가 들어간 konnichicha로 변경해주는 소스

```html
// HTML
<p class = "change_greeting">hello</p>
```

```html
//jQuery
$('.change_greeting').html('<b>konnichiha</b>');
```

```html
<!doctype html>
<html>
<head>
<meta charset ="utf-8"/>
<title>EVERDEVEL :: 제이쿼리 강좌</title>
<script type = "text/javascript">
$(function(){
    $('.change_greeting').html('<b>konnichiha</b>');
    });
});
</script>
</head>
<body>
<p class="change_greeting">hello</p>
</body>
</html>
```

**.html()**

Get the HTML contents of the fisrst element in the set of matched elements or set the HTML contents of every matched element.

This method does not accept any arguments.

If the selector expression matches more than one element, only the first match will have its HTML content returned. Consider this code:

```html
$("div.demo-containter").html();
```

In order for the following <div>'s content to be retrieved, it would have to be the first one with class="demo-containter" in the document.

```html
<div class ="demo-containter">
 <div class="demo-box">Demonstration Box</div>
 </div>	
```

The result would look like this:

```html
<div class = "demo-box">Demonstration Box</div>
```

Example

```html
//Click a paragraph to convert it from html to text.
</doctype html>
<head>
 <meta charset="utf-8"
 <title>html demo</title>
 <style>
 p {
     margin: 8px;
     font-size: 20px;
     color: blue;
     cursor: pointer;
 }
 b {
     text-decoration: underline;
 }
 button {
     cursor: pointer;
 }
 </stye>
 <script src ="https://code.jquery.com/jquery-1.10.2.js"></script>
 </head>
 <body>
 
 <p>
  <b>Click</b> to change the <span id ="tag">html</span>
  </p>
  <p>
   to a <span id ="text">text</span> node.
   </p>
   <p>
    This <button name="nada">button</button> does nothing.
    </p>
    
    <script>
    $("p").click(function(){
        var htmlString = $(this).html();
        $(this).text(htmlString);
    });
    </script>
    </body>
    </html>
```

**html(htmlString)**

Set the HTML contents of each element in the set of matched elements.

.html(htmlString)

A string of HTML to set as the content of each matched element.

.html(function)

A function returning the HTML content to set. Receives the index position of the element in the set and the old HTML value as arguments. jQuery empties the element before calling the function; use the oldhtml argument to reference the previous content. Within the function, this refers to the current element in the set.

```html
//Consider the following HTML;
<div class = "demo-containter">
 <div class ="demo-box">Demonstration Box</div>
</div>
```

```html
// The content of <div class="demo-containter">can be set like this.
    $("div.demo-containter")
      .html("<p>
    All new content. <em>You bet!</em>
    </p>));
    
// That line of code will replace everything inside <div class="demo-container">:
    <div class="demo-container">
        
        <p>
            All new content. <em>You bet!</em>
        </p>
    </div>
    
// As of jQuery 1.4 the .html() method allows the HTML content to be set by passing in a function
    $("div.demo-container").html(function() {
    var emphasis = "<em>" + $("p").length + "paragraphis!</em>";
    return "<p>All new content for " + emphasis + "</p>";
    });
```

Given a document with six paragraphs, this example will set the HTML of <div clas="demo-container"> to <p>All new content for <em>6 paragraphs! </em></p>.

Examples

```html
<!doctype html>
<html lang = "en">
<head>
 <meta charset="utf-8">
 <title>html demo</title>
 <style>
 .red {
     color:red;
 }
 </style>
 <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>

<span>Hello</span>
<div></div>
<div></div>
<div></div>

<script>
$("div").html("<span class='red'>Hello <b>Again</b></span>");

</body>
</html>
```

```html
//Add some html to each div then immediately do further manipulations to the inserted html.
<!doctype html>
<html lang="en">
<head>
<meta charset = "utf-8">
<title>html demo</title>
<style>
div {
    color: blue;
    font-size:18px;
}
</style>
<script src="https://code.jquery.com/jquery-1.10.2.js">
</head>
<body>

<div></div>
<div></div>
<div></div>

<script>
$("div").html("<b>Wow!</b> Such excitement...");
$("div b")
.append(document.createTextNode("!!!"))
.css("color","red");
</script>

</body>
</html>
```

**.append()  & .appendTo()**



**.append()**

Insert contetn, specified by the parameter, to the end of each element in the set of matched elements. 

The .append() method inserts the specified content as the last child of each element in the jQuery collection (To insert it as the first child, use .prepend() ).

The .append() and . appendTo() methods perform the same task. The major difference is in the syntax-specifically, in the placement of the content and target. With . append(), the selector expression preceding the method is the container into which the content is inserted. With .appendTo(), on the other hand, the content precedes the methods, either as a selector expression or as markup created on the fly, and it is inserted into the target container.



```html
// Consider the following HTML :
<h2>Greetings</h2>
<div class="container">
 <div class="inner">Hello</div>
 <div class="inner">Goodby</div>
</div> 
```

```html
// You can create content and insert it into several elements at once:
$(".inner").append("<p>Test</p>");

// Each inner <div> element gets this new content:
<h2>Greetings</h2>
    <div class="container">
        Hello
        <p>
           Test
        </p>
    </div>
    <div class="inner">
        Goodbye
     <p>Test</p>
    </div>
</div>
```

```html
//You can also select an element on the page and insert it into another
$(".container").append($("h2"));
```

```html
// If an element selected this way is inserted into a single location elsewhere in the DOM, it will be moved into the target (not cloned):
<div class="container">
<div class="inner">Hello</div>
<div class="inner">Goodbbye</div>
<h2>Greetings</h2>
<div>
```

**Important**: If there is more than one target element, however, cloned copies of the inserted element will be created for each target except for the last one.

Since .append() can accept any number of additional arguments, the same result can be achieved by passing in the three <div> s as three separate arguments, like so: $('body').append($newdiv1, newdiv2, existingdiv1). The type and number of arguments will largely depend on how you collect the elements in your code.

Examples:

Appends some HTML to all paragraphs.

```
<!doctype html>
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>append demo</title>
 <style>
 p {
     background:yellow;
 }
 </style>
 <script src="http://code.jquery.com/jquery-1.10.2.js">
 </head>
 <body>
 <p> I would like to say: </p>
 
 <script>
 $("p").append("<strong>Hello</stroing>");
 </scritp>
 </body>
 </html>
```

```html
//Appends an Element to all paragraphs.
<!doctype html>
<html lang ="en">
<head>
 <meta charset="utf-8">
 <title>append demo</title>
 <style>
 p {
     background : yellow;
 }
 </style>
 <script src="https://code.jquery.com/jquery-1.10.2.js">
 </head>
 <body>
 
 <p>I would like to say: </p>
 
 <script>
 $("p").append(document.createTextNode("Hello"));
 </script>
 </body>
 </html>
```

```html
//Appends a jQuery object(similar to an Array of DOM Elements)to all paragraphs.
<!doctype html>
<head>
 <meta charset="utf-8">
 <title>append demo</title>
 <style>
 p {
     background : yellow;
 }
 </style>
 <script src="https://code.jquery.com/jquery-1.10.2.js">
 </head>
 <body>
 
 <strong>Hello world!!!</strong>
 <p>I would like to say: </p>
 <script>
 $("p").append($("strong"));
 </script>
 </body>
 </html>
```

**.appendTo()**

.appendTo(target)  Insert every element in the set of matched elements to the end of the target.

```html
// Consider the following HTML :
<h2>Greetings</h2>
<div class="container">
 <div class="inner">Hello</div>
 <div class="inner">Goodbye</div>
</div>

// We can create content and insert it into several elements at once:
$("<p>Test</p>").appendTo(".inner");

//Each dinner <div> element gets this new content:
<h2>Greetings</h2>
<div class="container">
 <div class="inner">
  Hello
  <p>Test</p>
  </div>
  <div class="inner">
   Goodby
   <p>Test</p>
   </div>
 </div>
 
 //We can also select an element on the page and insert in into anotehr.
 
 $("h2").appendTo($".container"));
    
    ...
```

 Example:

Append all spans to the element with the ID "foo" (Check append() documentation for more examples)

```html
<!doctype html>
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>appendTo demo</title>
 <style>
 #foo {
     background: yellow;
 }
 </style>
 <script src ="https://code.jquery.com/jquery-1.10.2.js">
 </head>
 <body>
 
 <span>I have nothing more to say... </span>
 <div id="foo">FOO!</div>
 
 <script>
 $("span").appndTo("#foo");
 </script>
 
 </body>
 </html>
```

**.prepend()**

Insert content, specified by the parameter, to the beginning of each element in the set of matched elements.

The .prepend() method inserts the specified content as the first child of each element in the jQuery collection (To insert it as the last child, use .append()).

The .prepend() and .prepndTo() methods perform the same task. The major difference is in the syntax-specifically, in the placement of the content and target. With .prepnd(), the selector expression preceding the method is the container into which the content is inserted. With .prepndTo(), on the other hand, the content precedes the method, either as a selector expression or as markup created on the fly, and it is inserted into the target contianer.

```html
//Consider the following HTML:
<h2>Greetings</h2>
<div class="container">
 <div class="inner">Hello</div>
 <div class="inner">Goodbye</div>
 </div>
 
 // You can create content and insert it into several elements at once:
 $(".inner").prepend("<p>Test</p>");
 
 // Each <div class= "inner"> element gets this new content:
     <h2>
         Greetings
     </h2>
     <div class="container">
     <div class="inner">
         <p>Test</p>
         Hello
         </div>
         <div class="inner">
         <p>Test</p>
         Goodbye
         </div>
     </div>
```

Examples:

```html
//Prepends some HTML to all paragraphs.
<html lang="en">
<head>
 <meta charset="utf-8">
 <title> prepend demo</title>
 <style>
 p {
     background: yellow;
 }
 </style>
 <script src="https://code.jquery.com/jquery-1.10.2.js">
 </head>
 <body>
 
 <p>there, friend!</p>
 <p> amigo!</p>
 
 <script>
 $("p").prepend("<b>Hello<b>");
 </script>
 
 </body>
 </html>

```

```html
// Prepends a DOM Element to all paragraphs.

<!doctype html>
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>prepend demo</title>
 <style>
 p {
     background:yellow;
 }
 </style>
 <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>

<p>is what I'd say</p>
<p>is what I said</p>

<script>
$("p").prepend(document.createTextNode("Hello "));
</script>

</body>
</html>
```

```html
​``` Prepends a jQuery object(similar to an Array of DOM Elements)to all paragraphs.
<!doctype html>
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>prepend demo</title>
 <style>
 p {
     background: yellow;
 }
 </style>
 <script src= "https://code.jquery.com/jquery-1.10.2.js">
 </head>
 <body>
 
 <p> is what was said.</p><b>Hello</b>
 
 <script>
 ${("p").prepend($("b"));
 </script>
 </body>
 </html>
 
```

**.prependTo()**

Insert every element in the set of matched elements to the beginning of the target.

```html
// Consider the following HTML:
<h2>Greetings</h2>
<div class="containter">
 <div class="inner">Hello</div>
 <div class="inner>Goodbye</div>
</div>
             
// We can create content and insert it into several elements at once:
  $("<p>Test</div></p>").prependTo(".inner");

// Each inner <div> element gets this new content.
<h2>
    Greetings
    </h2>
    <div class="containter">
        <p>
            Test
        </p>
        Hello
    </div>
    <div class="inner">
        <p>
            Test
        </p>
        Goodbye
    </div>
</div>
```

```html
// We can also select an element on the page and insert it into another:
$("h2").prependTo($(".container"));

// If an element selected this way is inserted into a single location elsewhere in the DOM, it will be moved into the target (not cloned):

<div class="container">
    <h2>
        Greetings
    </h2>
    <div class="inner">
        Hello
    </div>
    <div class ="inner">
         Goodbye
    </div>
</div>
```

Example:

```html
<!doctype html>
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>prependTo demo</title>
 <style>
 div {
     background:yellow;
 }
 </style>
 <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>

<div id="foo">FOO!</div>
<span>I have something to say...</span>

<script>
$("span").prependTo("#foo");
</script>

</body>
</html>
```



**.remove()**

Remove the set of matched elements from the DOM.

Use .remove() when you want to remove the element itself, as well as everything inside it. In addition to the elements themselves, all bound events and jQuery data associated with the elements are removed. To remove the elements without removing data and events, use .detach() instead.

```html
//Consider the following HTML:
<div class="container">
 <div class="hello">Hello</div>
 <div class="goodbye">Goodbye</div>
</div>

//We can target any element for removal:
$(".hello").remove();

//This will result in a DOM structure with the <div> element deleted:
<div class="container">
 <div class="goodbye">Goodbye</div>
 </div>
```

If we had any number of nested elements inside <div class="hello">, they would be removed, too. 

```html
//We can also include a selector as an optional parameter. For example, we could rewrite the previous DOM removal code as follows.
$("div").remove(".hello");

//This would result in the same DOM structure:
<div class="container">
 <div class="goodbye">Goodbye</div>
 </div>
```

Examples:

```html
// Removes all paragraphs from the DOM
<!doctype html>
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>remove demo</title>
 <style>
 p {
     background:yellow;
     margin: 6px 0;
 }
 </style>
 <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>

<p>Hello</p>
how are
<p>you?</p>
<button>Call remove() on paragraphs</button>

<script>
$("button").click(function() {
    $("p").remove();
});
</script>
</body>
</html>
```

```html
//Removes all paragraphs that contain "Hello" from the DOM. Analogous to doing $("p").filter(":contains('Hello')").remove().

<!doctype html>
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>remove demo</title>
 <style>
 p {
     background: yellow;
     margin: 6px 0;
 }
 </style>
<script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>

<p class="hello">Hello</p>
how are
<p>you?</p>
<button>Call remove(" :contains('Hello')") on paragraphs</button>

<script>
$("button").click(function(){
    $("p").remove(":contains('Hello')");
});
</script>
</body>
</html>
```

