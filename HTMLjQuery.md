## JavaScript와의 접목 (HTML, CSS)

#### 1. 필요한 이유?

정적인 HTML의 요소들을 JavaScript를 이용해 변화를 줄 수도 있고, 버튼을 클릭했을 때 어떤 일이 일어날지 지정해 줄 수도 있다. 

#### 2. 사용법

자바스크립트를 사용하기 위해서는 script태그를 이용. head태그와 body태그 내부에 script가 모두 들어간다.   head태그에 들어가는 script는 보통 초기화를 위해서 사용. 그리고 body태그의 끝에 들어가는 script에는 페이지 기능에 관한 코드를 작성. body의 끝부분에 script를 넣는 이유는 html, css를 모두 불러온 후 script를 작동시키기 때문에 페이지 로딩이 빨리지기 때문.

**document** 는 문서 전체를 의미

**getElementById**는 해당 id값의 element를 반환해 주는 메소드.

<body>

 <h1>Hello World</h1>

<button onclick = "alert('안녕'!)"> event handler를 이용

**이벤트 핸들러**: 자바스크립트에는 이벤트 핸들러라고, 엘리먼트에 이벤트를 추가하는 방법이 있다. 그것이 바로 "on+이벤트명" (이하 on 이벤트)을 이용하는 법과 "addEvenListener()" 함수를 이용하는 법인데 이에 대해 간단하게 알아보자. 우선 on 이벤트의 사용 방법은 아래와 같다.

```javascript
element.onclick = function () {
    // Some codes in here
};
```

예를 들어 <div id = "box"></div>인 엘리먼트에 이벤트를 추가하고 싶을 경우 아래와 같은 방법으로 사용할 수 있다.

```javascript
const box = document.getElementById("box");

box.onclick = function() {
    alert("This is box");
};
```



### jQuery

먼저 index.html을 생성한 후 아래의 코드를 작성

```javascript
<!DOCTYPE html>

<html>
 <head>
 <script src = "https://code.jquery.com/jquery-3.2.1.min.js"></script> // jQuery를 사용한다는 뜻
 </head>
 <body>
  <h1>jQuery를 연습해 봅시다</h1>
  <script>
  $(document).ready(function(){  // document가 준비가 되면(로딩이 끝나면) 하위 코드를 실행합니다.
      //코드를 작성한 곳
  });
  </script>
 </body>
</html>

```

 이제 'jQuery를 연습해 봅시다'라는 글에 마우스를 올렸을 때, 색이 변하게 해봅시다.

```javascript
<!DOCTYPE html>

<html>
 <head>
 <script src = "https://code.jquery.com/jquery-3.2.1.min.js"></script> // jQuery를 사용한다는 뜻
 <title>jQuery연습</title>
 </head>
 <body>
  <h1 id="title">jQuery를 연습해 봅시다</h1>   // 먼저 id를 title로 지정해 줍니다.
  <script>
  $(document).ready(function(){  
     $('#title')  // CSS의 선택자를 기억하고 있나요? id값이 title인 DOM을 호출합니다.
         .on('mouseover',function(){ mouseover 이벤트가 발생할 때 실행하는 함수입니다.
          $(this)[0].style.color = 'red'; // $(this)[0]는 선택된 객체이고, style의                        
         color를 red로 바꿔줍니다.         
       })
         .on('mouseleave',function() {    // 마우스가 떠났을 때에는 원래의 색깔로 돌려줘        야 하므로
          $(this)[0].style.color='black';  //mouseleave 이벤트가 발생했을 때의 코드를 작성해 줍니다.         
     })
    });
  </script>
 </body>
</html>
```



Dom이란?

DOM은 문서 객체 모델(The Document Object Model)의 약자로, 프로그래밍 언어로 문서 내부의 객체들을 다룰 수 있게 도와주는 역할을 합니다. 예를 들어, id가 title인 객체를 불러오기 위해서는 document.getElementById('title');와 같이 불러올 수 있습니다. jQuery에선 이 문장을 $('#title')[0]으로 간결하게 끝낼 수 있습니다. $('선택자')와 같이 사용하면 선택자에 해당하는 모든 DOM들을 배열과 비슷한 형태로 불러옵니다. 그러므로 $('#title')[0]와 같이 뒤에 [0]을 붙여주어야 DOM에 접근이 가능합니다.

```javascript
<!DOCTYPE html>

<html>
 <head>
 <script src = "https://code.jquery.com/jquery-3.2.1.min.js"></script> // jQuery를 사용한다는 뜻
 <title>jQuery연습</title>
 </head>
 <body>
  <h1 id="title">jQuery를 연습해 봅시다</h1>   // 이렇게 줄여쓰는 것도 가능합니다.
  <script>
  $(document).ready(function(){  
     $('#title')  
        .mouseover(function() {}
        $(this)[0].style.color = 'red';   
       })
         .mouseleave(function() {    
         $(this)[0].style.color='black';  
     })
    });
  </script>
 </body>
</html>
```

하지만 이러면 문제점이 있습니다. 바로 이미 로딩된 객체들에게만 이 코드가 작동한다는 점. 무슨 뜻인지 직접 해보며 알아갑시다!

```javascript
<!DOCTYPE html>

<html>
 <head>
 <script src = "https://code.jquery.com/jquery-3.2.1.min.js"></script> // jQuery를 사용한다는 뜻
 <title>jQuery연습</title>
 </head>
 <body>
  <h1 class="practice">jQuery를 연습해 봅시다</h1>   
  <script>
  $(document).ready(function(){  
  	setInterval(function() {  // 3000ms(3초)마다 함수를 실행.
      $('body').append($('<h2 class='practice'>연습</h2>')); //body에 practice class를 가진 h2 DOM을 추가시켜 줍니다.
  	},3000);
     $('.practice')  
        .mouseover(function() {}
        $(this)[0].style.color = 'red';   
       })
         .mouseleave(function() {    
         $(this)[0].style.color='black';  
     })
    });
  </script>
 </body>
</html>
```

이제 html파일을 실행시키고, 3초 뒤에 나타나는 '연습!'에 마우스를 올려봅시다! 아무리 마우스를 올려도 색이 변하지 않습니다. 왜냐하면 페이지가 로딩될 때에는 $('practice')가 가리키는 DOM이 h1 태그 하나였기 때문. 그럼 어떻게?

정답은 바로 $('body')에 이벤트를 거는 것 입니다.

```html
<!DOCTYPE html>

<html>
 <head>
 <script src = "https://code.jquery.com/jquery-3.2.1.min.js"></script> // jQuery를 사용한다는 뜻
 <title>jQuery연습</title>
 </head>
 <body>
  <h1 class="practice">jQuery를 연습해 봅시다</h1>   
  <script>
  $(document).ready(function(){  
  	setInterval(function() {  
      $('body').append($('<h2 class='practice'>연습</h2>')); 
  	},3000);
     
     $('body')
     .on('mouseover','practice',function(){
         $(this)[0].style.color='red';
     })
     .on('mouseleave','.practice',function(){
         $(this)[0].style.color ='black';
     })
    });
  </script>
 </body>
</html>
```

 