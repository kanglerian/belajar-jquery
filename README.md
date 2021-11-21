# Getting Started with JQuery

The purpose of jQuery is to make it much easier to use JavaScript for building websites.
You can create animations and design interactive web pages using jQuery.

JQuery is a JavaScript library. It allows you to create various animation effects that HTML and CSS cannot accomplish alone. For example, jQuery can respond to events like clicks by hiding and showing HTML elements.

## Using Method

It's very simple and intuitive to work with jQuery: (1) creating a jQuery object and (2) calling a method (function) on that jQuery object.
Since jQuery is written in JavaScript, you need ; at the end of the sentence and use // for comments.

```javascript
$('selector').method(argument);
```

### jQuery Object

You can create a jQuery object by writing $('selector'). You can specify HTML tags and classes for the selector. Since jQuery selectors are the same as selectors used in CSS, you can work with them intuitively if you already have CSS knowledge.

```javascript
$('h1');
```

```HTML
<h1>jQuery</h1>
```

```CSS
h1 {
  color: red;
}
```

### jQuery.hide() method

Methods are convenient functions that are available to jQuery objects. They allow you to change the HTML elements contained in jQuery objects. You can call a method like: $('selector').method().
Let's first try hiding an element using the hide() method.

```javascript
$('h1').hide();
```

## Adding Animation

The fadeOut() method is similar to the hide() method. The fadeOut() method allows you to animate elements to be hidden and specify the animation's speed as an argument inside (). You can specify the speed in milliseconds or with a character string (for example, "slow").

```javascript
$('selector').fadeOut();
```

```javascript
$('selector').fadeOut(1500); //1500 is 1.5 seconds.
```

```javascript
$('selector').slideUp();
```

```javascript
$('selector').slideUp(1500); //1500 is 1.5 seconds.
```

## Classes and Id

Let's learn about the id attribute. It's very similar to classes that we learned in HTML, but unlike classes, the same id cannot be used more than once. The example below shows how to use the ids and classes in HTML.

```HTML
.
.
.
<ul id="list">
  <li class="list-item">list 1</li>
  <li class="list-item">list 2</li>
</ul>
.
.
.
``

```CSS
#list {
  margin: 10px;
}
.list-item {
  color: blue;
}
```

```javascript
$('#list').css('margin','20px');
$('.list-item').css('color','red');
```

## Showing an Element

CSS has what is called the display property. You can use this property to hide elements by default, like: display: none;.
(For details on the display property, see HTML & CSS Ⅱ).

```CSS
img {
  display: block; // nampak
}
h1 {
  display: none; // tidak nampak
}
```

```CSS
img {
  display: none;
}
```

```javascript
$('img').show();
```

### fadeIn 

```javascript
$('selector').fadeIn();
$('selector').fadeIn('slow');
```

## The "click" event

With events, you can set the specific timing to perform a certain action. For example, you can specify an event to be executed whenever someone clicks a button on the web page.
The syntax for events is as follows: $('selector').event(function(){ });

```javascript
$('selector').event(function(){
  // your code
});
```

### click Event

Using the click event, you can specify an event to occur when the selector is clicked. For example, you can add an event to hide some text when a button is clicked.

```HTML
<div id="hide-text">Hide text</div>
<p id="text">Click the button to hide the text.</p>
```

```javascript
$('#hide-text').click(function(){
  $('text').hide();
});
```

## The "css" Method

The css() method allows you to modify CSS using jQuery.
To use this method, set the CSS property to the first argument, and the value of the property to the second argument.

```javascript
$('selector').css('property','value');
```

```CSS
p {
  color: blue;
}
```

```javascript
$('p').css('color','red');
```

### Hidding Element with the css() Method

You can change the value of the display property using the css() method. $('selector').css('display', 'none'); works exactly the same as the hide() method. Remember that both the hide() method and show() method only change the value of the display property.

```HTML
<img src="unknown.jpg">
```

```CSS
img {
  display: none;
}
```

```javascript
$('img').css('display','block');
```

### Latihan

```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
</head>
<body>
  <!-- Add the id "change-css" to the <div> tag -->
  <div id="change-css" class="btn">Change CSS</div>
  
  <h1 id="text">Hello, World!</h1>
  
  <script src="script.js"></script>

</body>
</html>
```

```css
.btn {
  display: inline-block;
  cursor: pointer;
  padding: 12px 80px;
  background-color: #5dca88;
  box-shadow: 0px 5px #279C56;
  border-radius: 3px;
  color: #fff;
  font-size: 12px;
}

.btn:active {
  position: relative;
  top: 5px;
  box-shadow: none;
}
```

```javascript
$(function() {
  // Add click() method for #change-css
  $('#change-css').click(function(){
    $('#text').css('color', 'red');
    $('#text').css('font-size', '50px');
  });
    
});
```

## The "text" and "html" Methods

### Changing HTML - text Method

With jQuery, you can also change the text inside an HTML element using the text() method. You use the text() method as follows: $('selector').text('new text');.

```HTML
<p>Hello</p>
```

```javascript
$('p').text('Goodbye');
```

```javascript
$('p').html('<span>Goodbye</span>');
```

### Latihan

```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
</head>
<body>
  <!-- Add the id "change-text" to the <div> tag -->
  <div class="btn" id="change-text">Change text</div>
  
  <!-- Add the id "change-html" to the <div> tag -->
  <div class="btn" id="change-html">Change HTML</div>
  
  <h1 id="text">Hello, World!</h1>
  
  <script src="script.js"></script>

</body>
</html>
```

```CSS
.btn{
  display: inline-block;
  cursor: pointer;
  padding: 8px 30px;
  background-color: #5dca88;
  box-shadow: 0px 5px #279C56;
  border-radius: 3px;
  color: #fff;
  font-size: 10px;
}

.btn:active{
  position: relative;
  top: 5px;
  box-shadow: none;
}
```

```javascript
$(function() {
  // Add a click() method for #change-text
  $('#change-text').click(function(){
    $('#text').text('Hello, Progate!');
  });
  
  // Add a click() method for #change-html
  $('#change-html').click(function(){
    $('#text').html('<a href="https://progate.com/">Hello, Progate!</a>');
  });
  
});
```

## Using "this"

The this keyword can extract an element where an event occurs. Keep in mind that we do not enclose this in " or ' marks. You will see $(this) quite often throughout this course since it is a very useful and important concept.

```HTML
<ul>
  <li>List 1</li>
  <li>List 2</li>
  <li>List 3</li>
</ul>
```

```javascript
$('li').click(function(){
  $(this).css('color', 'red');
})
```

![](/img/jQuery-this1.png)
![](/img/jQuery-this.gif)

### Latihan

```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
</head>
<body>
  <ul>
    <!-- Add the class "list-item" to all the <li> tags -->
    <li class="list-item">List 1</li>
    <li class="list-item">List 2</li>
    <li class="list-item">List 3</li>
  </ul>
  
  <script src="script.js"></script>

</body>
</html>
```

```CSS
li {
  cursor: pointer;
}
```

```Javascript
$(function() {
  // Add a click() method for .list-item
  $('.list-item').click(function(){
    $(this).css('color', 'red');
  });
  
});
```

## Variables and Method Chaining

When using the same jQuery object more than once, you should use a variable for faster processing. Like JavaScript, jQuery uses var for variable declaration. When storing jQuery objects, we usually add a $ to the beginning of the variable name as a convention.

### Variables

Without Variables

```javascript
$('div').css('color','red');
$('div').html('jQuery');
$('div').fadeOut();
```

With Variables

```javascript
var $div = $('div');

$div.css('color','red');
$div.html('jQuery');
$div.fadeOut();
```

### Using Method Chaining

When using the same jQuery object more than once, you can also use method chaining to speed up processing. Method chaining refers to successively applying multiple methods to the same jQuery object.
The syntax for it is as follows: $('selector').method1().method2()....

```javascript
$('div').css('color','red').html('jQuery');
$('div').fadeOut();
```

### Latihan

```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
</head>
<body>
  <div class="btn">Click!</div>
  
  <h1 id="title">Hello, Ken!</h1>
  
  <p id="text">Welcome to Progate!</p>
  
  <script src="script.js"></script>

</body>
</html>
```

```CSS
.btn {
  display: inline-block;
  cursor: pointer;
  padding: 12px 80px;
  background-color: #5dca88;
  box-shadow: 0px 5px #279C56;
  border-radius: 3px;
  color: #fff;
  font-size: 12px;
}

.btn:active {
  position: relative;
  top: 5px;
  box-shadow: none;
}
```

```Javascript
$(function() {
  $('.btn').click(function() {
    // Assign the jQuery object for #title to the $title variable
    var $title = $('#title');              
    
    // Rewrite the following using the $title variable:
    $title.css('color', 'red');
    $title.html('Goodbye, Ken!');
    $title.fadeOut(1000);
    
    // Rewrite the following using method chaining:
    $('#text').css('color', 'blue').html('<h3>See you soon!</h3>').fadeOut(1000);
  });
});
```

## The "find" and "children"

The find() method finds the specified element from all the elements inside that element. The example below shows how you can extract all <a> elements inside #wrapper.

## Find Method

Semua link akan berwarna merah.

```HTML
<div class="wrapper">
  <a href="#">Link 1</a>
  <p>
    <a href="#">Link 2</a>
  </p>
</div>
```

```javascript
$('#wrapper').find('a').css('color','red');
```

## Children Method

Hanya link pertama saja yang akan berwarna merah.

```HTML
<div class="wrapper">
  <a href="#">Link 1</a>
  <p>
    <a href="#">Link 2</a>
  </p>
</div>
```

```javascript
$('#wrapper').children('a').css('color','red');
```

### Latihan

```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
</head>
<body>
  <!-- Add the id "find-method" -->
  <div class="btn" id="find-method">find</div>
  
  <!-- Add the id "children-method" -->
  <div class="btn" id="children-method">children</div>
  
  <div id="wrapper">
    <a href="#">Link 1</a>
    <div>
      <a href="#">Link 2</a>
    </div>
  </div>

  <script src="script.js"></script>

</body>
</html>
```

```CSS
.btn {
  display: inline-block;
  cursor: pointer;
  width: 180px;
  padding: 12px 0;
  background-color: #5dca88;
  box-shadow: 0px 5px #279C56;
  border-radius: 3px;
  color: #fff;
  font-size: 12px;
  margin-bottom: 20px;
  text-align: center;
}

.btn:active {
  position: relative;
  top: 5px;
  box-shadow: none;
}

#wrapper {
  margin-top: 30px;
}
```

```javascript
$(function() {
  $('#find-method').click(function() {
    // Use the find() method to get all the <a> elements inside #wrapper,
    // then change the color to red using the css() method
    $('#wrapper').find('a').css('color','red');
    
    
  });
  
  $('#children-method').click(function() {
    // Use the children() method to get the <a> elements directly inside #wrapper,
    // then hide them using the fadeOut() method
    $('#wrapper').children('a').fadeOut();
    
    
  });
});
```

## Creating a Hover Event

The hover event binds handlers for both mouse-enter and mouse-leave events. Let's display a message only when the mouse is on the text "What is jQuery? using the hover event!

### Implementing hover event

The syntax for hover is like: `$('selector').hover(function1, function2);`.
The first argument is for mouse-enter, and the second is for mouse-leave. Make sure to separate the arguments with `,`.

```javascript
$('div').hover(
  function(){

  },
  function(){

  }
);
```

### Latihan

```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
</head>
<body>
  <div id="language-wrapper">
    <h1 class="language-title">What is jQuery?</h1>
    <p class="language-text">
      jQuery is a fast, easy-to-use JavaScript library that handles animations and Ajax requests.
    </p>
  </div>

  <script src="script.js"></script>

</body>
</html>
```

```CSS
/* Change language-text's display property to none */
.language-text{
  display:none;
}
```

```javascript
$(function() {
  // Add the hover() method for #language-wrapper
  $('#language-wrapper').hover(
    function() {
      $('.language-text').fadeIn();
    },
    function() {
      $('.language-text').fadeOut();
    }
  );
  
});
```

# JQuery Study II

**Adding JQuery to your page**
To use jQuery, you need to load the jQuery library. You can do this by loading the URL in the <head> tag (see the example below).
It's common for libraries to be loaded via the Internet like this.

```HTML
<head>
  <script src="https://..jquery.min.js"></script>
</head>
```

```HTML
<head>
  <script src="script.js"></script>
</head>
```

## Document Ready Event

Since jQuery changes HTML elements, you need to make sure that the HTML document is loaded before running any jQuery code. You can do this by writing your jQuery code inside the ready event. The syntax for the ready event is $(document).ready(), or you can use the shorthand syntax $(function(){});.

```javascript
$(document).ready(function(){
  // your code
});
```

```javascript
$(function(){
  // your code
});
```

## Creating Modals

Let's create a modal that you can display or hide by clicking a button. A modal is an element that is displayed/hidden based on actions like click events.

### Displaying Modals

We'll use the login button in the header as the trigger to open a modal. The steps will be: (1) hide the modal by default using CSS (2) set a click event on the login button, and (3) display the modal in the click event.

```CSS
.login-modal-wrapper {
  .
  .
  display:none;
}
```

```javascript
$('#login-show').click(function(){
  $('#login-modal').fadeIn();
});
```

#### Latihan

```HTML
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Progate</title>
  <link rel="stylesheet" type="text/css" href="stylesheet.css">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
</head>
<body>
  <header>
    <div class="container">
      <div class="header-left">
        <img class="logo" src="https://prog-8.com/images/html/advanced/main_logo.png">
      </div>
      <div class="header-right">
        <!-- Add the id "login-show" to the <div> tag -->
        <div class="login" id="login-show">Log in</div>
        
      </div>
    </div>
  </header>
  <div class="signup-modal-wrapper">
  </div>
  <!-- Add the id "login-modal" -->
  <div class="login-modal-wrapper" id="login-modal">
    <!-- Paste the HTML for the login modal -->
    <div class="modal">
      <div id="login-form">
        <h2>Log in with email</h2>
        <form action="#">
          <input class="form-control" type="text" placeholder="Email">
          <input class="form-control" type="password" placeholder="password">
          <div id="submit-btn">Log in</div>
        </form>
      </div>
    </div>
    
  </div>
  <div class="top-wrapper">
    <div class="container">
      <h1>LEARN TO CODE.<br>LEARN TO BE CREATIVE.</h1>
      <p>Progate is a web service where you can learn programming online.<br>We offer you a fully equipped coding environment to get you started.</p>
      <div class="btn signup">Sign up with Email</div>
      <p>or</p>
      <div class="btn facebook"><span class="fa fa-facebook"></span>Sign up with Facebook</div>
      <div class="btn twitter"><span class="fa fa-twitter"></span>Sign up with Twitter</div>
    </div>
  </div>
  <div class="lesson-wrapper">
    <div class="container">
      <div class="heading">
        <h2>Learn Where to Get Started!</h2>
      </div>
      <div class="lessons">
      </div>
    </div>
  </div>
  <div class="faq-wrapper">
    <div class="container">
      <div class="heading">
        <h2>FAQ</h2>
      </div>
      <div class="faq">
      </div>
    </div>
  </div>
  <div class="message-wrapper">
    <div class="container">
      <div class="heading">
        <h2>Ready to become an awesome programmer?</h2>
        <h3 id="tagline">Let's learn to code, learn to be creative!</h3>
      </div>
      <div class="btn message">Start Learning</div>
    </div>
  </div>
  <footer>
    <div class="container">
      <img src="https://prog-8.com/images/html/advanced/footer_logo.png">
      <p>Learn to code, learn to be creative.</p>
    </div>
  </footer>
  <script src="script.js"></script>
</body>
</html>
```

```CSS
body {
  margin: 0;
  font-family: "Lucida Grande";
}

a {
  text-decoration: none;
}

.top-wrapper {
  padding: 180px 0 100px 0;
  background-image: url(https://prog-8.com/images/html/advanced/top.png);
  background-size: cover;
  color: white;
  text-align: center;
}

.container {
  width: 1170px;
  padding: 0 15px;
  margin: 0 auto;
}

.top-wrapper h1 {
  opacity: 0.7;
  font-size: 45px;
  letter-spacing: 5px;
}

.top-wrapper p {
  opacity: 0.7;
  font-size: 14px;
  margin-bottom: 35px;
}

.signup {
  background-color: #239b76;
}

.facebook {
  background-color: #3b5998;
  margin-right: 10px;
}

.twitter {
  background-color: #55acee;
}

.btn {
  padding: 8px 24px;
  color: white;
  display: inline-block;
  opacity: 0.8;
  border-radius: 4px;
  cursor: pointer;
}

.btn:hover {
  opacity: 1;
}

.fa {
  margin-right: 5px;
}

header {
  height: 65px;
  width: 100%;
  background-color: rgba(34,49,52,0.9);
  position :fixed;
  top: 0;
  z-index: 10;
}

.logo {
  width: 124px;
  margin-top: 20px;
}

.header-left {
  float: left;
}

.header-right {
  float: right;
  background-color: rgba(255,255,255,0.3);
  transition: all 0.5s;
}

.header-right:hover {
  background-color: rgba(255,255,255,0.5);
}

.header-right .login {
  line-height: 65px;
  padding: 0 25px;
  color: white;
  cursor: pointer;
  display: block;
}

/* Modal */
/* Paste the CSS for the modal */
.login-modal-wrapper {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.6);
  z-index: 100;
  /* Change the display property to none */
  display: none;
}

.modal {
  position: absolute;
  top: 20%;
  left: 34%;
  background-color: #e6ecf0;
  padding: 20px 0 40px;
  border-radius: 10px;
  width: 450px;
  height: auto;
  text-align: center;
}

.fa-times {
  position: absolute;
  top: 12px;
  right: 12px;
  color: rgba(128, 128, 128, 0.46);
  cursor: pointer;
}

#signup-form, #login-form {
  width: 100%;
}

#signup-form h2, #login-form h2 {
  color: #5f5d60;
  letter-spacing: 1px;
  margin-bottom: 40px;
}

#signup-form input, #login-form input {
  width: 320px;
  margin-bottom: 20px;
  font-size: 12px;
  padding: 12px 12px;
  border: 1px solid #d0d5d8;
  border-radius: 5px;
}

#submit-btn {
  display: inline-block;
  padding: 14px 140px;
  background-color: #5dca88;
  border: none;
  border-radius: 3px;
  color: white;
  margin: 10px auto;
  cursor: pointer;
}



.lesson-wrapper {
  height: 500px;
  padding-bottom: 80px;
  background-color: #f7f7f7;
  text-align: center;
}

.heading {
  padding-top: 60px;
  padding-bottom: 30px;
  color: #5f5d60;
}

.heading h2 {
  font-weight: normal;
}

/* FAQ wrapper */
.faq-wrapper {
  background-color: #e6ecf0;
  text-align: center;
  padding-bottom: 80px;
  color: #5f5d60;
}

#faq-list {
  width: 500px;
  margin: 0 auto;
  padding: 0;
  list-style: none;
}

.message-wrapper {
  border-bottom: 1px solid #eee;
  padding-bottom: 80px;
  text-align: center;
}

.message-wrapper .heading h3 {
  font-weight: normal;
}

.message {
  padding: 15px 40px;
  background-color: #5dca88;
  cursor: pointer;
  box-shadow: 0px 7px #1a7940;
}

.message:active {
  position: relative;
  top: 7px;
  box-shadow: none;
}

footer img {
  width: 125px;
}

footer p {
  color: #b3aeb5;
  font-size: 12px;
}

footer {
  padding-top: 30px;
}
```

```javascript
$(function() {
  // Add a click() method for #login-show
  $('#login-show').click(function(){
    $('#login-modal').fadeIn();
  });
  
});
```

### Hiding Modal

```HTML
<div class="close-modal">
  <i class="fa fa-2x fa-times"></i>
</div>
```

```javascript
$(function() {
  // Add a click() method for #login-show
  $('#login-show').click(function(){
    $('#login-modal').fadeOut();
    $('#signup-modal').fadeOut();
  });
  
});
```

### Using Hover

You can use the hover event to display the text description about each lesson when the mouse hovers over the lesson icon. As you can see in the example below, the texts are hidden by default.

Let's prepare the hover event as follows:
(1) add a class called lesson-hover to each lesson icon
(2) set the hover event for .lesson-hover in script.js.

```HTML
<div class="lesson lesson-hover">

</div>
```

```javascript
$('.lesson-hover').hover(
  function(){

  },
  function(){
    
  }
);
```

### "addClass" and "removeClass"

We will use the text-active class shown below to display/hide the text when the mouse hovers over a lesson icon. To do this, we will:
(1) add .text-active{display: block;} in the CSS.
(2) add the text-active class on mouse-enter.
(3) remove text-active class on mouse-leave.

The addClass() method allows you to add a class to an element. Using the addClass() method, you can add the class text-active to an element with the text-contents class.

```HTML
<p class="text-contents">...</p>
```

```JavaScript
$('.text-contents').addClass('text-active');
$('.text-contents').removeClass('text-active');
```

### Making Accordions

Finally, we'll add an accordion for the FAQ list. Our FAQ interface will have a smooth sliding animation that shows/hides the answer to a question. We will use if statements for the accordion, so review our JavaScript course if you don't remember them!

The steps to create an accordion are:
(1) Hide the answers by default with CSS.
(2) Add click events to all the questions using the same class.
(3) Add/remove the open class to the answer to show/hide them.

```HTML
<div class="answer">...</div>
<div class="answer open">...</div>
```

#### hasClass() Method

We use the hasClass() method to determine whether or not an element has a certain class. It will return true or false. We'll use this to determine if the answer is currently open or not.

```HTML
<div class="answer">...</div>
<div class="answer open">...</div>
```

```Javascript
$('.answer').hasClass('open');
// return false
$('.answer open').hasClass('open');
// return true
```

```Javascript
$('.faq-list-item').click(function(){
  var $answer = $(this).find('.answer');
  if($answer.hasClass('open')){
    $answer.removeClass('open');
  }else{
    $answer.addClass('open');
  }
});
```

Menambahkan + - di accordions

```Javascript
$('.faq-list-item').click(function(){
  var $answer = $(this).find('.answer');
  if($answer.hasClass('open')){
    $answer.removeClass('open');

    $answer.slideUp();
    $(this).find('span').text('+');

  }else{
    $answer.addClass('open');

    $answer.slideDown();
    $(this).find('span').text('-');

  }
});
```