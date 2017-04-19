---
title: Lesson 10
permalink: /lesson_10
---

# Lesson 10

### This Lesson's Focus: Javascript And jQuery *(continued)*
* Practice! (doesn't make perfect, but it gets you closer)


### At CoderGirl
* Work Time
* Quick Talk/Activity: Reading Code


### Course Work

#### Assignment: Cat Lady Scale Challenge
**Do**: See directions in the GitHub Project...  
[Cat Lady Scale Challenge](https://github.com/LaunchCoderGirlSTL/cat_lady_scale)


#### Assignment: Cake Project - Use Javascript to make a Reusable Header and Footer
**Intro:** You have a beautiful and functional cake website.  But your work is never over! One problem you may have noticed was you needed to manually copy your header and footer. This works fine but can cause problems for a real world website that is constantly changing. Imagine the cake business changed their hours of operation, they want to close on Sundays. Lets say you made the changes on each page, but accidentally forgot to change one of the footers! You might end up with some really unhappy customers on Sunday.  To fix this problem we are going to create our headers and footers in one place, then when you need to change it, it will change on all pages. To accomplish this we are going to use your new javascript knowledge and build the header and footer in a javascript file. Then we can include this javascript on each page and it will include the same header and footer on every page.

**STEP 1**  
Create a new js file (or use your existing javascript file). Create some test code (maybe do an alert("hello") or a console.log("hi") to make sure the code is executing).

**STEP 2**  
Create your html header as a string. For example, imagine your html header looks like this:
```
<nav>
    <ul>
        <li>Menu</li>
        <li>Custom</li>
        <li>About</li>
        <li>Hours</li>
    </ul>
</nav>
```
We could also represent this same html in javascript as a string, something like:
```
var header = "<nav> <ul> <li>Menu</li> <li>Custom</li> <li>About</li> <li>Hours</li> </ul> </nav>";
```
Or we could use javascript string concatenation to do the same things like this:  
*(just remember if you use this method, the addition signs have to be at the end of the line, otherwise javascript thinks you are missing a semi-colon)*
```
var header = "<nav>" +
    "<ul>" +
        "<li>Menu</li>" +
        "<li>Custom</li>" +
        "<li>About</li>" +
        "<li>Hours</li>" +
    "</ul>" +
"</nav>";
```
We are going to create this string in javascript and insert it into our html.

**STEP 3**  
To insert our javascript string into our html page, we can use the jQuery html() function.
Learn about using the jquery `html()` function in the [jquery docs](http://api.jquery.com/html/).

You can call html() on a jQuery element to return the html that is inside that element. Or you can use the `html(htmlString)` version that will replace the content inside that element with string you pass to the html function. This is the version we will use.

**STEP 4**  
Now use the `html(htmlString)` function to insert the content of your header into your html. To do this, you are going to need an empty header element in your html. Select that element with jQuery and call html() on the element, passing the rest of your htmlString. Beware, if you want to use classes or ids in your html string, you will need to use single quotes inside of the double quotes, like this:
```
var htmlString = "<div class='nav'></div>"
```
**STEP 5**  
Do this same thing for the footer and for every other page.

**STEP 6**  
Now you can change your header or footer in one place and those changes will be reflected on all of the pages!


#### Assignment: Cake Project - Using JSON to make our cake site dynamic
**Intro**: Most websites have some kind of dynamic content, content on a webpage that is not written directly in the HTML.  Instead dynamic content is usually HTML that is generated based on some external data source. Why would you want to do that? Well, imagine our cake site wanted to have a daily special. As a web developer, we don't want be have to manually update our HTML daily just to change the special. It would be much better to instead, dynamically create our HTML based off an external data source that had the information for the daily special.  It is much easier to change that data than it is to change the HTML. With dynamic content we can easily update our data and our HTML will be automatically changed. Most websites you use on a day to day basis use a lot of dynamic content and is the heart of a modern web app.

There are a few different ways to create dynamic content on the web. The most common approach is to dynamically generate HTML on a server, this is how a "server side" website works. But we are learning front end development and want to create our dynamic content using javascript.  This is a "client side" approach to dynamic content, and is becoming a more and more popular way to build a web application. There is a **lot** more to learn about dynamic websites, but for now we will be starting with the simplest possible example. Our data is going to be a simple JSON file. Our javascript will read that JSON data, do some simple computations on the data, and output some HTML.

First, a quick explanation on JSON. JSON (pronounced jay-son or jason) is a simple and standard way to store data that is easy for both humans and computers to read and write. JSON stands for JavaScript Simple Object Notation, and the exact syntax of JSON data is basically a simplified javascript object (which pretty much explains the name). JSON is a widely used data format used on the web and it a very common way to exchange data and communicate between a server and a client.

Don't worry if this all still seems a little confusing. Trust me, we have all been confused by this. Make sure to ask your web mentors if you are confused about dynamic content, JSON, or where a webserver/database would come into this picture.

**Note:** Don't try to accomplish this task in one go, make sure you are testing your code at each step! For example, to make sure you are reading the JSON file, `console.log(the parsed json)`. Or to see if `$.each()` is working like you expect `console.log(each-item)` in the function you passed to each. Nobody ever gets it right on the first try, good programmers are really just good debuggers!

**Do**: There is a inventory.json file in your repository containing a JSON list of items. We are going to use javascript to read each item, group items by their type, and then insert each item's name and description into our webpage.

**STEP 1**  
Read this article about the [JSON format](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON)  

**STEP 2**  
js - read the json file and store it in a javascript variable.  It should come in as an array of items. jQuery provides a useful function called [getJson](http://api.jquery.com/jquery.getjson/) to read a json file and turn it into a js object.  

**STEP 3**  
js - figure out how to loop over the array of all inventory items.  We need to determine if each item is either a 'cake' or something else. Sort each item into different arrays, one array for cakes and one array for other things. The [$.each](http://api.jquery.com/jquery.each/) function may be useful here, or you can use a more traditional javascript for loop to loop over each item in the array.  

**STEP 4**  
js - Now should have two arrays with different items. Our goal now is to turn each item into a string of HTML that we can use to insert into our HTML page. Something like [$.map](http://api.jquery.com/jquery.map/) could be useful to transform your array of javascript objects into an array of strings. Or you could use the `$.each` function or for loop again. There are many different ways to accomplish this, but the goal is to start tuning those javascript items into strings of HTML that we can insert into the HTML.

**STEP 5**  
js - insert the strings of HTML into your actual HTML document. You might want to insert each item one at a time as you loop over the array of items, or you may want to build two larger HTML strings (one with all of the cake items and one with all of the other items) and insert the two separate HTML strings after you are done looping over them, do it whichever way you find easier.


[Home]( /web_group_cohort )
