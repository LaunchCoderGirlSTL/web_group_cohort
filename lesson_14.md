---
title: Lesson 14
permalink: /lesson_14
---

# Lesson 14

### This Lesson's Focus: Learning React
React is a Javascript Framework.

### Course Work

#### Assignment: Take a React Course + Trello React Challenge
This time while taking the CodeSchool React course you are going to pair it with a project. You should take 1 React Level then complete 1 Project Challenge as described below. I would recommend completing the "Getting Started" part of the project before starting the first course level.

[CodeSchool - Powering Up with React](https://www.codeschool.com/courses/powering-up-with-react)  
[Trello Project](https://github.com/LaunchCoderGirlSTL/trello_react_project)

#### Getting Setup
1) FORK... don't forget to FORK this repo first! Then, once you have this project in your own GitHub account... clone it to your computer.

2) Checkout the file structure...  
assets - contains a css directory with the css for the site AND a js directory that holds a bundle.js file (more about this file later)

design - holds an image of the final page

src - holds an app.jsx and a components.jsx file. these are your react files where you will write your react components and implement your React App.

> make sure to look through these files... components.jsx holds one component CardColumn which currently renders and empty div. Then at the bottom of the page there is an export statement (remember this from your ES2015 class!) that exports the component (aka, makes it visible for use in other jsx files). The app.jsx file imports the CardColumn, creates a MainPage component, and then puts it into the index.html file...

gulpfile.js - Remember CodeSchool talking about React and ES2015 not being able to display directly in browsers? no? Well, both react which use jsx and ES2015, have to be compiled into regular Javascript before they can be displayed in your web browser. We are going to use a tool called gulp to do this. This gulpfile.js takes our src/app.jsx file transforms it into the bundle.js file we saw in the assets/js directory. Then we can just link the bundle.js file into our index.html... and we have our React Application up and running!

index.html - our html file :) check it out...

package.json - a file that defines what node packages our gulpfile uses (you will see how to use this in a little bit)

3) To get our application up and running we need to install somethings...

**Node Install**: in your command line run `node -v` to see if you have node already installed on your computer. If you do not have node install following these instructions:

[Mac Users - Install Instructions](http://blog.teamtreehouse.com/install-node-js-npm-mac)  
[Windows Users - Install Instructions](http://blog.teamtreehouse.com/install-node-js-npm-windows)

**Installing Node Packages for This Project**: From your terminal or command line, navigate to inside this project. Enter `ls` to make sure you see all the files in this project like package.json or the assets directory. Now run `npm install`.
> npm install will install all the tools you need for this project that are defined in the package.json file.

**Compiling Your React Application**: Now that everything is installed let's run a `gulp build`. This command will compile your jsx or React file into that bundle.js we were talking about. You will have to run this command everytime you change your jsx file.

> There is a way to automate this... like have gulp watch your react files and every time they change it will automatically run gulp for you... however, I think it is better for you to run this command yourself at first, so you know how it works.

Cool! You should now be able to open the index.html file in Chrome and be on your way!


#### CodeSchool Level 1 - First Component
Complete Level 1 of React Fundamentals courses...

#### React Challenge 1 - Create Card Component
Take a look at what the site is going to look like:
<img width="100%" src="images/trello-design-1.png" />

First you are going to create your card component...

Create a Card Component in the components.jsx file (remember to extend the React Component Base Class)...

> With regular Javascript, we had to use HTML String to construct html elements... With React, we use JSX to construct our HTML. JSX lets us write HTML in Javascript with some additional features…

Create a render function in the Card Component Class with the appropriate HTML used to generate each card... there is a reference to what the html for a card is suppose to look like in the index.html file.
> Remember *class* is a reserved word in Javascript so we have to use className=“” instead of class=“” in each of our html elements

> JSX makes it easier to create HTML in Javascript because it lets us combine HTML and Javascript, rather than having us construct strings...
{} -> literal javascript

For Example: remember when we had to do this...

```
var behaviorItem = ‘<div class=“behavior”>’ +
    ‘<div class=“name”>’ + behavior.name + ‘</div>’ +
    ‘<div class=“value”>’ + behavior.value + ‘</div>’ +
‘</div>’;

$(‘behavior-list’).html(behaviorItem);
```

... well now we can just do this...

```
return (
    <div>
        <div className=“name”>{ behavior.name }</div>
        <div className=“value”>{ behavior.value }</div>
    </div>
);
```

...much more readable, a lot less addition signs and a lot less quotes!

Render your Card Component: Inside the <div></div> in the CardColumn component... render your newly created card component with the `<Card />` syntax;

Then open your terminal, navigate to your project, run `gulp build` and refresh your index.html in the browser. Is your card displaying?!

#### CodeSchool Level 2 - Talking Through Props
Complete Level 2 of React Fundamentals courses...

#### React Challenge 2 - Construct 2nd Component & Pass Data
Watch React LEVEL 2...

**1) Identifying Other Components**  
Name the other components you see in the below Design:
<img width="100%" src="images/trello-design-1.png" />

now, we are going to create our 2nd component... CardColumn.

**2) Create a Card Column Component**  
Again make sure it extends the React.Component base class... implement the render function based on the html that is in the index.html file. Make sure to use `<Card />` instead of the actual card html. This will use whatever the render function of your Card Component returns.

**3) Passing Props from the CardColumn Component to the Card Component**   
In the card component, pass the Card component 2 props... I bet you can guess what they are! (title and description)

Then update the Card Components render function to use those props…
calling out `{this.props.title}` and `{this.props.description}`

**4) Use Card Data Array to display the cards**  
In the CardColumn component, create a `_getCards` function with a cardList array with card objects that have id, title, and description properties.

> Typically, in a React Application you would make an ajax request to the backend, where the cards would be queried and passed back to you on the FrontEnd. For now, we are just creating a cardList array to simulate the information we would get back from the ajax request.

> Wondering why this function starts with an underscore? The `_functionName` is just a naming convention that React uses to indicate that the function should only be accessible INSIDE the Component it is defined in.

**5) Map Object array to JSX arrays for display purposes**  
Now in the `_getCards` function, map over the cardList array and return JSX `<Card />` components with the props key, title, description.

> The key prop is used to make each card component unique. This becomes helpful when the user goes to interact with a card, like clicks a button on it, React will have a way to determine which card is clicked based on this key id.

**6) Use _getCards() in CardColumn render()**  
The `_getCards()` function will return a list of Card components for us. So we can replace all the `<Card />` in the CardColumn render function with the returned results from the `_getCards` function.

**7) Compile your React Code!**
Open your terminal, navigate to your project and run `gulp build`. Refresh your index.html in your web browser! See if something is displaying!


#### CodeSchool Level 3 - Component State
Complete Level 3 of React Fundamentals courses...

#### React Challenge 3 - Implement the Card States
So in this React Level it talked about direct vs indirect DOM manipulation. Direct DOM manipulation is what we have been doing with jQuery, we select and change the actual html elements or the actual CSS.

React uses indirect DOM manipulation. React components use “states” to describe things that might change in a component or to describe data that might change over time.
> Direct vs Indirect DOM manipulation  
> Direct - like jQuery -> directly change html elements and css properties with JS and/or jQuery  
> Indirect - like React -> modify state with javascript -> React notices updated state -> so then it updates the DOM for you   

Components use “states” to describe things that might change in a component… data that might change over time

Can you think of a “state” that might helpful in determining whether or not our card should show the green > button?

We are going to add 2 states to our card...  

STATE: complete (boolean)  
_goal:_ if complete is false show the green arrow > button, and if it is true do not show the button.  
_action:_ the green arrow > button should mark a card complete  

STATE: archive (boolean)  
_goal:_ if archive is false show the card like usual, if archive is true do NOT show the card.  
_action:_ the red x button should mark a card archived  

Let's get started.

**1) Initialize the State in the Constructor**  
First we need to create a constructor for our card class. It will need:  
-- a call to the parent constructor with `super();`  
> we must call super() function to make sure it’s parent constructor is called first. After all, a child can’t be created before a parent!

-- to initialize the card components state object `this.state = {};`

> "this" keyword refers to the component in which you are using it in...

-- add the complete state (I'll let you guess at what the initial boolean value should be)


**2) Updating the State**  
now we need function that updates the state we just initialized
-- create a `_markComplete` function that updates the card’s complete state to TRUE.

> Remember to use the this.setState({}) function to update the state. We use this function instead of directly modifying the components state to trigger a certain response from React. Using the setState function tells the React Component that it has to re-render the Component. If we just modified this.state directly, we would lose this behavior.

> You might be wondering where this function comes from? Our card class “inherits” the React.Component class… this class holds a bunch of functions that any react component would need. setState() is just one of them. You can checkout other common functions and behaviors that React.Component brings to each defined class [here](https://facebook.github.io/react/docs/react-component.html)

**3) Connecting a User Action to Change State**  
Now we can use the `_markComplete` function when the user clicks the green arrow button...  
-- add an `onClick` attribute that calls the `_markComplete` function on to the green arrow button element in `render()`  

> don’t forget to use .bind(this) on the function… if you are wondering about this whole binding thing, [this article](https://www.smashingmagazine.com/2014/01/understanding-javascript-function-prototype-bind/) does a pretty good job of explaining it.

**4) Updating Card render based on state**
Now we are ready to change the Card’s appearance based on the complete state. We want to hide the green arrow button if the card is already marked complete.  

-- In the render section, create a variable called `completeButton`, if card is not complete, set it to the green arrow JSX.

-- Use the new `completeButton` variable in the returned JSX code block.

**5) CHECK RESULTS! remember to gulp build.**
If there are compile errors, you will see them printed in the console whern you run `gulp build`.

**6) Repeat steps for the ARCHIVE state**  
-- initialize in constructor  
-- create a function to update that state  
-- connect the function to a user action  
-- change how the card renders based on the archive state (hide the card completely)




#### CodeSchool Level 4 - Synthetic Events
Complete Level 2 of React Fundamentals courses...

#### React Challenge 4 - TBD




#### CodeSchool Level 5 - Talking To Remote Servers
Complete Level 2 of React Fundamentals courses...

#### React Challenge 5 - TBD



[Home]( /web_group_cohort )
