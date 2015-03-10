# Explain the animate function.

-The animate function is used to apply the custom animation effect to elements.

-Syntax:

$(selector).animate({params}, [duration], [easing], [callback])

“param” defines the CSS properties on which you want to apply the animation.
“duration” specify how long the animation will run. It can be one of following values : “slow”, “fast”, “normal” or milliseconds
“easing” is the string which specify the function for the transition.
“callback” is the function which we want to run once the animation effect is complete.

# What is the use of param() method.

The param() method is used to represent an array or an object in serialize manner.
While making an ajax request we can use these serialize values in the query strings of URL.
Syntax: $.param(object | array, boolValue)
“object | array” specifies an array or an object to be serialized.
“boolValue” specifies whether to use the traditional style of param serialization or not.
For example:

personObj=new Object();
empObject.name="Arpit";
empObject.age="24";
empObject.dept=”IT”;
$("#clickme").click(function(){
$("span").text($.param(empObject));
});
It will set the text of span to “name=Arpit&age=24&dep=IT”

# What is jQuery.holdReady() function?

-By using jQuery.holdReady() function we can hold or release the execution of jQuery’s ready event.
-This method should be call before we run ready event.
-To delay the ready event, we have to call

jQuery.holdReady(true);

-When we want to release the ready event then we have to call
jQuery.holdReady(false);
-This function is helpful when we want to load any jQuery plugins before the execution of ready event.

For example

$.holdReady(true);
$.getScript("xyzplugin.js", function() {
$.holdReady(false);
});

# Explain .empty() vs .remove() vs .detach().

-.empty() method is used to remove all the child elements from matched elements.
-.remove() method is used to remove all the matched element. This method will remove all the jQuery data associated with the matched element.
-.detach() method is same as .remove() method except that the .detach() method doesn’t remove jQuery data associated with the matched elements.
-.remove() is faster than .empty() or .detach() method.

Syntax:

$(selector).empty();
$(selector).remove();
$(selector).detach();

# How to read, write and delete cookies in jQuery?

-To deal with cookies in jQuery we have to use the Dough cookie plugin.
-Dough is easy to use and having powerful features.
-Create cookie

$.dough("cookie_name", "cookie_value");

Read Cookie
$.dough("cookie_name");
Delete cookie
$.dough("cookie_name", "remove");

# What is Chaining in jQuery?

- Chaining is very powerful feature of jQuery.
- Chaining means specifying multiple function and/or selectors to an element.
- Examine the below example

$(document).ready(function(){
$('#mydiv').css('color', 'blue');
$('#mydiv').addClass('myclass');
$('#mydiv').fadeIn('fast');
}

By using chaining we can write above code as follows

$(document).ready(function(){
$('#mydiv').css('color', 'blue').addClass('myclass').fadeIn('fast');
});

-Advantage of chaining is that it makes your code simple and simple to manage.
-The execution becomes faster because the code search for the element only once.

# What are the types of selectors that are used in jquery? Give examples.

Jquery enables the user to select specifically the element that is to be effected. jquery allows the user to select in the following ways:
- jquery element selectors: with the use of css selectors the users can select the elements of an html document.
For ex. 
$("p") will select all the <p> elements.
$("p.intro") will select all <p> elements with class="intro" defined in them.
$("p#demo") this will select all <p> elements with id="demo".
-jquery attribute selectors: the xpath expressions are used by jquery to select elements of an html document with defined attributes.
For ex.
$("[href]") is used to select all elements which have an href attribute.
$("[href$='.jpg']") can select all elements with an href attribute which will end with ".jpg".

# What are the various ajax functions ?

Ajax allows the user to exchange data with a server and update parts of a page without reloading the entire page. Some of the functions of ajax are as follows:
- $.ajax(): This is considered to be the most low level and basic of functions. It is used to send requests . This function can be performed without a selector. 
- $.ajaxSetup(): This function is used to define and set the options for various ajax calls. 
For ex. 
$.ajaxSetup({ 
"type":"POST", 
"url":"ajax.php", 
"success":function(data){ 
$("#bar") 
.css("background","yellow") 
.html(data); 
} 
}); 
- Shorthand ajax methods: They comprise of simply the wrapper function that call $.ajax() with certain parameters already set.
- $.getJSON(): this is a special type of shorthand function which is used to accept the url to which the requests are sent. Also optional data and optional callback functions are possible in such functions.
