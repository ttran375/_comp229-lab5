# Weekly Learning Outcome #1: 

-   Describe page setup
-   Create html Document using react
-   requirements for working with React in the browser
-   Discuss React Elements
-   Create Elements
-   The type and props field
-   Describe how to use props.children
-   Describe classname in React
-   Constructing Elements with Data

# How React Works  

## Topic Content

<a href="How%20React%20WorksN.pptx?isCourseFile=true" target="_self">How
React WorksN.pptx</a>

<a href="WEEK2-HOWREACTWORKS.zip?isCourseFile=true"
target="_self">WEEK2-HOWREACTWORKS.zip</a>

<a href="How%20React%20Works.docx?isCourseFile=true" target="_self">How
React Works.docx</a>

# How React Works  

<span style="text-decoration: underline; font-size: 20px;">**HOW REACT
WORKS**</span>

<span style="font-size: 20px;">When you work with React, it’s more than
likely that you’ll be creating your apps with a syntax called JSX. JSX
is a tag-based JavaScript syntax that looks a lot like HTML.</span>

<span style="font-size: 20px;">To truly understand React though, we need
to understand its most atomic units:</span>

-   <span style="font-size: 20px;">React elements.</span>

-   <span style="font-size: 20px;">React components.</span>

-   <span style="font-size: 20px;">Fiber and how React makes efficient
    choices about rendering and
    reconciliation.</span><span style="font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

# Page Setup  

<span style="text-decoration: underline; font-size: 20px;">**Page
Setup**</span>

<span style="font-size: 20px;">Inorder to work with React in the
browser, we need to include two libraries:</span>

1.  <span style="font-size: 20px;">React and</span>
2.  <span style="font-size: 20px;">ReactDOM.</span>

  
<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React is the library for creating
views.</span>

<span style="font-size: 20px;">ReactDOM is the library used to actually
render the UI in the browser.</span>

<span style="font-size: 20px;">Both libraries are available as scripts
from the unpkg CDN.</span>

<span style="font-size: 20px;"></span>

# HTML Document Setup with React:  

<span style="text-decoration: underline; font-size: 20px;">**HTML
Document Setup with React**</span>

# setting up an HTML document  

``` html
<!DOCTYPE html>
<html> 
<head>
<meta charset="utf-8" /> 
<title>React Samples</title>
</head> 
<body>
<!-- Target container --> 
<div id="root"></div>
<!-- React library & ReactDOM (Development Version)-->
<script
src="https://unpkg.com/react@16.8.6/umd/react.development.js"></script> 
<script src="https://unpkg.com/react-dom@16.8.6/umd/react-
dom.development.js"></script>
<script>
// Pure React and JavaScript code
</script> 
</body>
</html>
```

# Requirements for working with React in the browser : 

<span style="text-decoration: underline; font-size: 20px;">**Requirements
for working with React in the browser **</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="font-size: 20px;">These are the minimum requirements for
working with React in the browser.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">You can place your JavaScript in a
separate file, but it must be loaded somewhere in the page after React
has been loaded.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">We’re going to be using the development
version of React to see all of the error messages and warnings in the
browser console.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">You can choose to use the minified
production version using react.production.min.js and
react-dom.production.min.js which will strip away those warnings.</span>

# React Elements  

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**React
Elements**</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">HTML is simply a set of instructions that
a browser follows when constructing the document object model, </span>

<span style="font-size: 20px;">or DOM.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The elements that make up an HTML
document become DOM elements when the browser loads HTML and renders the
user interface.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">To construct an HTML hierarchy for a
recipe. A possible solution for such a task might look something like
this:</span>

<span style="text-decoration: underline; font-size: 20px;">**HTML
hierarchy for a recipe**</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="font-size: 20px;">\<section id="baked-salmon"\></span>

<span style="font-size: 20px;">\<h1\>Baked Salmon\</h1\></span>

<span style="font-size: 20px;">\<ul class="ingredients"\></span>

<span style="font-size: 20px;">\<li\>2 lb salmon\</li\></span>

<span style="font-size: 20px;">\<li\>5 sprigs fresh
rosemary\</li\></span>

<span style="font-size: 20px;">\<li\>2 tablespoons olive
oil\</li\></span>

<span style="font-size: 20px;">\<li\>2 small lemons\</li\></span>

<span style="font-size: 20px;">\<li\>1 teaspoon kosher
salt\</li\></span>

<span style="font-size: 20px;">\<li\>4 cloves of chopped
garlic\</li\></span>

<span style="font-size: 20px;">\</ul\></span>

<span style="font-size: 20px;">\<section class="instructions"\></span>

<span style="font-size: 20px;">\<h2\>Cooking Instructions\</h2\></span>

<span style="font-size: 20px;">\<p\>Preheat the oven to 375
degrees.\</p\></span>

<span style="font-size: 20px;">\<p\>Lightly coat aluminum foil with
oil.\</p\></span>

<span style="font-size: 20px;">\<p\>Place salmon on foil\</p\></span>

<span style="font-size: 20px;">\<p\>Cover with rosemary, sliced lemons,
chopped garlic.\</p\></span>

<span style="font-size: 20px;">\<p\>Bake for 15-20 minutes until cooked
through.\</p\></span>

<span style="font-size: 20px;">\<p\>Remove from oven.\</p\></span>

<span style="font-size: 20px;">\</section\></span>

<span style="font-size: 20px;">\</section\></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">In HTML, elements relate to each other in
a hierarchy that resembles a family tree.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">We could say that the root element (in
this case a section) has three children:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">I. a heading,</span>

<span style="font-size: 20px;">II. an unordered list of
ingredients,</span>

<span style="font-size: 20px;">III. and a section for the
instructions.</span>

<span style="font-size: 20px;">The DOM API is a collection of objects
that JavaScript can use to interact with the browser to modify the
DOM.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">If you have used document.createElement
or document.appendChild, you have worked with the DOM API.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React is a library that is designed to
update the browser DOM for us.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">We no longer have to be concerned with
the complexities associated with building high-performing SPAs because
React can do that for us.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">With React, we do not interact with the
DOM API directly. Instead, we provide instructions for what we want
React to build and React will take care of rendering and reconciling the
elements that we have instructed it to create.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The browser DOM is made up of DOM
elements. Similarly, the React DOM is made up of React elements.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">DOM elements and React elements may look
the same, but they are actually quite different.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">A React element is a description of what
the actual DOM element should look like.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React elements are the instructions for
how the browser DOM should be created.</span>

<span style="font-size: 20px;">We can create a React element to
represent an h1 using React.createElement:</span>

<span style="font-size: 20px;">React.createElement("h1",  {  id:
"recipe-0" },  "Baked Salmon");</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The first argument defines the type of
element that we wish to create. In this case, we want to create an h1
element.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The second argument represents the
element’s properties. This h1 currently has an id of recipe-0.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The third argument represents the
element’s children, any nodes that are inserted between the opening and
closing tag, in this case just some text.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">During rendering, React will convert this
element to an actual DOM element:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">\<h1 id="recipe-0"\>Baked
Salmon\</h1\></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The properties are similarly applied to
the new DOM element:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">the properties are added to the tag as
attributes, and the child text is added as text within the
element.</span>

  
<span style="font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">A React element is just a JavaScript
literal that tells React how to construct the DOM element.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">If you were to log this element, it would
look like this:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">{</span>

<span style="font-size: 20px;">}</span>

<span style="font-size: 20px;">$$typeof: Symbol(React.element),</span>

<span style="font-size: 20px;">"type": "h1",</span>

<span style="font-size: 20px;">"key": null,</span>

<span style="font-size: 20px;">"ref": null,</span>

<span style="font-size: 20px;">"props": {id: "recipe-0",  children:
"Baked Salmon"},</span>

<span style="font-size: 20px;">"\_owner": null,</span>

<span style="font-size: 20px;">"\_store": {}</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">This is the structure of a React
element.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">These are fields that are used by React:
\_owner, \_store, $$typeof. The key and ref fields are important to
React elements.</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**The type
and props fields**</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The type property of the React element
tells React what type of HTML or SVG element to create.</span>

  
<span style="font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The props property represents the data
and child elements required to construct a DOM element.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The children property is for displaying
other nested elements as text.</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**CREATING
ELEMENTS **</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Use the React.createElement
function.</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

**<span style="text-decoration: underline; font-size: 20px;">ReactDOM</span>**

**<span style="text-decoration: underline; font-size: 20px;"></span>**

<span style="font-size: 20px;">Once we have created a React element,
we’ll want to see it in the browser.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">ReactDOM contains the tools necessary to
render React elements in the browser.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">ReactDOM is where we will find the render
method.</span>

<span style="font-size: 20px;">We can render a React element, including
its children, to the DOM with ReactDOM.render.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The element that we wish to render is
passed as the first argument and the second argument is the target node,
where we should render the element:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">const dish = React.createElement("h1", 
null,  "Baked Salmon");</span>

<span style="font-size: 20px;">ReactDOM.render(dish,document.getElementById("root"));</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Rendering the title element to the DOM
would add an h1 element to the div with the id of root, which we would
already have defined in our HTML. We build this div inside the body
tag:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">\<body\></span>

<span style="font-size: 20px;">\<div id="root"\></span>

<span style="font-size: 20px;">\<h1\>Baked Salmon\</h1\></span>

<span style="font-size: 20px;">\</div\></span>

<span style="font-size: 20px;">\</body\></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Anything related to rendering elements to
the DOM is found in the ReactDOM package.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">In versions of React earlier than React
16, you could only render one element to the DOM. Today, it’s possible
to render arrays as well.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">const dish = React.createElement("h1", 
null,  "Baked Salmon");</span>

<span style="font-size: 20px;">const dessert =
React.createElement("h2",  null,  "Coconut Cream Pie");</span>

<span style="font-size: 20px;">ReactDOM.render(\[dish,  dessert\],
document.getElementById("root"));</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">This will render both of these elements
as siblings inside of the root container.</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**How to use
props.children.**</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="font-size: 20px;"><span style="text-decoration: underline;"></span></span>

<span style="font-size: 20px;"><span style="text-decoration: underline;"></span>Children</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React renders child elements using
props.children. In the previous section, we rendered a text element as a
child of the h1 element, and thus props.children was set to Baked
Salmon.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">We could render other React elements as
children too, creating a tree of elements.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The tree has one root element from which
many branches grow.</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**Example:**</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">consider the unordered list that contains
ingredients:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">\<ul\></span>

<span style="font-size: 20px;">\<li\>2 lb salmon\</li\></span>

<span style="font-size: 20px;">\<li\>5 sprigs fresh
rosemary\</li\></span>

<span style="font-size: 20px;">\<li\>2 tablespoons olive
oil\</li\></span>

<span style="font-size: 20px;">\<li\>2 small lemons\</li\></span>

<span style="font-size: 20px;">\<li\>1 teaspoon kosher
salt\</li\></span>

<span style="font-size: 20px;">\<li\>4 cloves of chopped
garlic\</li\></span>

<span style="font-size: 20px;">\</ul\></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">the unordered list is the root element,
and it has six children.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">We can represent this ul and its children
with React.createElement:</span>

  
<span style="font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"ul",</span>

<span style="font-size: 20px;">null,</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2 lb
salmon"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "5
sprigs fresh rosemary"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
tablespoons olive oil"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
small lemons"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "1
teaspoon kosher salt"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "4
cloves of chopped garlic")</span>

<span style="font-size: 20px;">);</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Every additional argument sent to the
createElement function is another child element.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React creates an array of these child
elements and sets the value of props.children to that array.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Inspect the resulting React element, we
would see each list item represented by a React element and added to an
array called props.children.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">If you console log this element:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">const list = React.createElement(</span>

<span style="font-size: 20px;">"ul",</span>

<span style="font-size: 20px;">null,</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2 lb
salmon"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "5
sprigs fresh rosemary"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
tablespoons olive oil"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
small lemons"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "1
teaspoon kosher salt"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "4
cloves of chopped garlic")</span>

<span style="font-size: 20px;">);</span>

<span style="font-size: 20px;">console.log(list);</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The result will look like this:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">{</span>

<span style="font-size: 20px;">"type": "ul",</span>

<span style="font-size: 20px;">"props": {</span>

<span style="font-size: 20px;">"children": \[</span>

<span style="font-size: 20px;">{  "type": "li",  "props": {  "children":
"2 lb salmon" }  …    },</span>

<span style="font-size: 20px;">{  "type": "li",  "props": {  "children":
"5 sprigs fresh rosemary"}  …    },</span>

<span style="font-size: 20px;">{  "type": "li",  "props": {  "children":
"2 tablespoons olive oil" }  …    },</span>

<span style="font-size: 20px;">{  "type": "li",  "props": {  "children":
"2 small lemons"}  …    },</span>

<span style="font-size: 20px;">{  "type": "li",  "props": {  "children":
"1 teaspoon kosher salt"}  …    },</span>

<span style="font-size: 20px;">{  "type": "li",  "props": {  "children":
"4 cloves of chopped garlic"}  …    }</span>

<span style="font-size: 20px;">\]</span>

<span style="font-size: 20px;">...</span>

<span style="font-size: 20px;">}</span>

<span style="font-size: 20px;">}</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">each list item is a child</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">To create this using React, we’ll use a
series of createElement calls:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"section",</span>

<span style="font-size: 20px;">{  id: "baked-salmon" },</span>

<span style="font-size: 20px;">React.createElement("h1",  null,  "Baked
Salmon"),</span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"ul",</span>

<span style="font-size: 20px;">{  className: "ingredients" },</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2 lb
salmon"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "5
sprigs fresh rosemary"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
tablespoons olive oil"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
small lemons"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "1
teaspoon kosher salt"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "4
cloves of chopped garlic")</span>

<span style="font-size: 20px;">),</span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"section",</span>

<span style="font-size: 20px;">{  className: "instructions" },</span>

<span style="font-size: 20px;">React.createElement("h2",  null, 
"Cooking Instructions"),</span>

<span style="font-size: 20px;">React.createElement("p",  null,  "Preheat
the oven to 375 degrees."),</span>

<span style="font-size: 20px;">React.createElement("p",  null,  "Lightly
coat aluminum foil with oil."),</span>

<span style="font-size: 20px;">React.createElement("p",  null,  "Place
salmon on foil."),</span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"p",</span>

<span style="font-size: 20px;">null,</span>

<span style="font-size: 20px;">"Cover with rosemary, sliced lemons,
chopped garlic."</span>

<span style="font-size: 20px;">),</span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"p",</span>

<span style="font-size: 20px;">null,"Bake for 15-20 minutes until cooked
through."</span>

<span style="font-size: 20px;">),</span>

<span style="font-size: 20px;">React.createElement("p", null, "Remove
from oven.")</span>

<span style="font-size: 20px;">)</span>

<span style="font-size: 20px;">);</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**CLASSNAME
IN REACT**</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Any element that has an HTML class
attribute is using className for that property instead of class.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Since class is a reserved word in
JavaScript, we have to use className to define the class attribute of an
HTML element.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">This sample is what pure React looks
like. Pure React is ultimately what runs in the browser.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">A React app is a tree of React elements
all stemming from a single root element.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React elements are the instructions that
React will use to build a UI in the browser.</span>

# \>CONSTRUCTING ELEMENTS WITH DATA  

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**CONSTRUCTING
ELEMENTS WITH DATA**</span>

<span style="text-decoration-line: underline; font-size: 20px;"></span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The major advantage of using React is its
ability to separate data from UI elements.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Since React is just JavaScript, we can
add JavaScript logic to help us build the React component tree.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">For example, ingredients can be stored in
an array, and we can map that array to the React elements.</span>

# Example:  

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Example:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">the unordered list</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"ul",</span>

<span style="font-size: 20px;">null,</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2 lb
salmon"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "5
sprigs fresh rosemary"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
tablespoons olive oil"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "2
small lemons"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "1
teaspoon kosher salt"),</span>

<span style="font-size: 20px;">React.createElement("li",  null,  "4
cloves of chopped garlic")</span>

<span style="font-size: 20px;">);</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The data used in this list of ingredients
can be easily represented using a JavaScript array:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">const items = \[</span>

<span style="font-size: 20px;">"2 lb salmon",</span>

<span style="font-size: 20px;">"5 sprigs fresh rosemary",</span>

<span style="font-size: 20px;">"2 tablespoons olive oil",</span>

<span style="font-size: 20px;">"2 small lemons",</span>

<span style="font-size: 20px;">"1 teaspoon kosher salt",</span>

<span style="font-size: 20px;">"4 cloves of chopped garlic"</span>

<span style="font-size: 20px;">\];</span>

<span style="font-size: 20px;">We want to use this data to generate the
correct number of list items without having to hard code each
one.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">We can map over the array and create list
items for as many ingredients as there are:</span>

  
<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React.createElement("ul",</span>

<span style="font-size: 20px;">{  className: "ingredients" },</span>

<span style="font-size: 20px;">items.map(ingredient =\>
React.createElement("li", null, ingredient))</span>

<span style="font-size: 20px;">);</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">This syntax creates a React element for
each ingredient in the array.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">Each string is displayed in the list
item’s children as text.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">The value for each ingredient is
displayed as the list item.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">When running this code, you’ll see a
console warning </span>  
<span style="font-size: 20px;"></span>

<span style="font-size: 20px;"><img src="image_20230818063355.png" style="max-width: 100%;"
data-d2l-editor-default-img-style="true" /></span>

<span style="font-size: 20px;">When we build a list of child elements by
iterating through an array,</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React likes each of those elements to
have a key property. The key property is used by React to help it update
the DOM efficiently.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">You can make this warning go away by
adding a unique key property to each of the list item elements.</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">We can use the array index for each
ingredient as that unique value:</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">React.createElement(</span>

<span style="font-size: 20px;">"ul",</span>

<span style="font-size: 20px;">{  className: "ingredients" },</span>

<span style="font-size: 20px;">items.map((ingredient,  i)  =\></span>

<span style="font-size: 20px;">React.createElement("li",  {  key: i }, 
ingredient)</span>

<span style="font-size: 20px;">)</span>

<span style="font-size: 20px;">);</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">adding this to each list item will clear
the console warning.</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**Adjusted
code**</span>

<span style="font-size: 20px;"></span>

<span style="font-size: 20px;">\<!DOCTYPE html\></span>

<span style="font-size: 20px;">\<html\></span>

<span style="font-size: 20px;">\<head\></span>

<span style="font-size: 20px;">\<meta charset="utf-8" /\></span>

<span style="font-size: 20px;">\<title\>React Samples\</title\></span>

<span style="font-size: 20px;">\</head\></span>

<span style="font-size: 20px;">\<body\></span>

<span style="font-size: 20px;">  \<!-- Target container --\></span>

<span style="font-size: 20px;">  \<div id="root"\>\</div\></span>

  
<span style="font-size: 20px;">  \<!-- React library & ReactDOM
(Development Version) --\></span>

<span style="font-size: 20px;">  \<script
src="<https://unpkg.com/react@16.8.6/umd/react.development.js>"\>\</script\></span>

<span style="font-size: 20px;">  \<script
src="<https://unpkg.com/react-dom@16.8.6/umd/react-dom.development.js>"\>\</script\></span>

  
<span style="font-size: 20px;">  \<script\></span>

<span style="font-size: 20px;">    const items = \[</span>

<span style="font-size: 20px;">      "2 lb salmon",</span>

<span style="font-size: 20px;">      "5 sprigs fresh rosemary",</span>

<span style="font-size: 20px;">      "2 tablespoons olive oil",</span>

<span style="font-size: 20px;">      "2 small lemons",</span>

<span style="font-size: 20px;">      "1 teaspoon kosher salt",</span>

<span style="font-size: 20px;">      "4 cloves of chopped garlic"</span>

<span style="font-size: 20px;">    \];</span>

  
<span style="font-size: 20px;">    const list =
React.createElement(</span>

<span style="font-size: 20px;">      "ul",</span>

<span style="font-size: 20px;">      { className: "ingredients"
},</span>

<span style="font-size: 20px;">      items.map((ingredient, i)
=\></span>

<span style="font-size: 20px;">        React.createElement("li", { key:
i }, ingredient)</span>

<span style="font-size: 20px;">      )</span>

<span style="font-size: 20px;">    );</span>

  
<span style="font-size: 20px;">    ReactDOM.render(list,
document.getElementById("root"));</span>

<span style="font-size: 20px;">  \</script\></span>

<span style="font-size: 20px;">\</body\></span>

<span style="font-size: 20px;">\</html\></span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="text-decoration: underline; font-size: 20px;">**Output in
the Browser**</span>

<span style="text-decoration: underline; font-size: 20px;"></span>

<span style="font-size: 20px;"><span style="text-decoration: underline;"></span><img src="image_20230818063355.png" style="max-width: 100%;"
data-d2l-editor-default-img-style="true" /></span>

## Learning Activity

<span style="color: #085394;">Read the content related to this learning
outcome **and describe how react works also complete the practical as
described in the lecture slides .**</span>

# References

Chapter 4:Learning React, 2nd Edition by Alex Banks, Eve Porcello
Publisher: O'Reilly Media, Inc. Release Date: June 2020ISBN:
9781492051725; page 64-72/p\>

**COMP-229: Web Application Development**