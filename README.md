# How React Works  

## Topic Content

<a href="How%20React%20WorksN.pptx?isCourseFile=true" target="_self">How
React WorksN.pptx</a>

<a href="WEEK2-HOWREACTWORKS.zip?isCourseFile=true"
target="_self">WEEK2-HOWREACTWORKS.zip</a>

<a href="How%20React%20Works.docx?isCourseFile=true" target="_self">How
React Works.docx</a>

# How React Works  

**HOW REACT WORKS**

When you work with React, it’s more than likely that you’ll be creating
your apps with a syntax called JSX. JSX is a tag-based JavaScript syntax
that looks a lot like HTML.

To truly understand React though, we need to understand its most atomic
units:

- React elements.

<!-- -->

- React components.

<!-- -->

- Fiber and how React makes efficient choices about rendering and
  reconciliation.

# Page Setup  

**Page Setup**

Inorder to work with React in the browser, we need to include two
libraries:

1.  React and
2.  ReactDOM.

  

React is the library for creating views.

ReactDOM is the library used to actually render the UI in the browser.

Both libraries are available as scripts from the unpkg CDN.

# HTML Document Setup with React:  

**HTML Document Setup with React**

# setting up an HTML document  

setting up an HTML document:

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

**Requirements for working with React in the browser **

These are the minimum requirements for working with React in the
browser.

You can place your JavaScript in a separate file, but it must be loaded
somewhere in the page after React has been loaded.

We’re going to be using the development version of React to see all of
the error messages and warnings in the browser console.

You can choose to use the minified production version using
react.production.min.js and react-dom.production.min.js which will strip
away those warnings.

# React Elements  

**React Elements**

HTML is simply a set of instructions that a browser follows when
constructing the document object model, 

or DOM.

The elements that make up an HTML document become DOM elements when the
browser loads HTML and renders the user interface.

To construct an HTML hierarchy for a recipe. A possible solution for
such a task might look something like this:

**HTML hierarchy for a recipe**

\<section id="baked-salmon"\>

\<h1\>Baked Salmon\</h1\>

\<ul class="ingredients"\>

\<li\>2 lb salmon\</li\>

\<li\>5 sprigs fresh rosemary\</li\>

\<li\>2 tablespoons olive oil\</li\>

\<li\>2 small lemons\</li\>

\<li\>1 teaspoon kosher salt\</li\>

\<li\>4 cloves of chopped garlic\</li\>

\</ul\>

\<section class="instructions"\>

\<h2\>Cooking Instructions\</h2\>

\<p\>Preheat the oven to 375 degrees.\</p\>

\<p\>Lightly coat aluminum foil with oil.\</p\>

\<p\>Place salmon on foil\</p\>

\<p\>Cover with rosemary, sliced lemons, chopped garlic.\</p\>

\<p\>Bake for 15-20 minutes until cooked through.\</p\>

\<p\>Remove from oven.\</p\>

\</section\>

\</section\>

In HTML, elements relate to each other in a hierarchy that resembles a
family tree.

We could say that the root element (in this case a section) has three
children:

I. a heading,

II\. an unordered list of ingredients,

III\. and a section for the instructions.

The DOM API is a collection of objects that JavaScript can use to
interact with the browser to modify the DOM.

If you have used document.createElement or document.appendChild, you
have worked with the DOM API.

React is a library that is designed to update the browser DOM for us.

We no longer have to be concerned with the complexities associated with
building high-performing SPAs because React can do that for us.

With React, we do not interact with the DOM API directly. Instead, we
provide instructions for what we want React to build and React will take
care of rendering and reconciling the elements that we have instructed
it to create.

The browser DOM is made up of DOM elements. Similarly, the React DOM is
made up of React elements.

DOM elements and React elements may look the same, but they are actually
quite different.

A React element is a description of what the actual DOM element should
look like.

React elements are the instructions for how the browser DOM should be
created.

We can create a React element to represent an h1 using
React.createElement:

React.createElement("h1",  {  id: "recipe-0" },  "Baked Salmon");

The first argument defines the type of element that we wish to create.
In this case, we want to create an h1 element.

The second argument represents the element’s properties. This h1
currently has an id of recipe-0.

The third argument represents the element’s children, any nodes that are
inserted between the opening and closing tag, in this case just some
text.

During rendering, React will convert this element to an actual DOM
element:

\<h1 id="recipe-0"\>Baked Salmon\</h1\>

The properties are similarly applied to the new DOM element:

the properties are added to the tag as attributes, and the child text is
added as text within the element.

  

A React element is just a JavaScript literal that tells React how to
construct the DOM element.

If you were to log this element, it would look like this:

{

}

\$\$typeof: Symbol(React.element),

"type": "h1",

"key": null,

"ref": null,

"props": {id: "recipe-0",  children: "Baked Salmon"},

"\_owner": null,

"\_store": {}

This is the structure of a React element.

These are fields that are used by React: \_owner, \_store, \$\$typeof.
The key and ref fields are important to React elements.

**The type and props fields**

The type property of the React element tells React what type of HTML or
SVG element to create.

  

The props property represents the data and child elements required to
construct a DOM element.

The children property is for displaying other nested elements as text.

**CREATING ELEMENTS **

Use the React.createElement function.

**ReactDOM**

Once we have created a React element, we’ll want to see it in the
browser.

ReactDOM contains the tools necessary to render React elements in the
browser.

ReactDOM is where we will find the render method.

We can render a React element, including its children, to the DOM with
ReactDOM.render.

The element that we wish to render is passed as the first argument and
the second argument is the target node, where we should render the
element:

const dish = React.createElement("h1",  null,  "Baked Salmon");

ReactDOM.render(dish,document.getElementById("root"));

Rendering the title element to the DOM would add an h1 element to the
div with the id of root, which we would already have defined in our
HTML. We build this div inside the body tag:

\<body\>

\<div id="root"\>

\<h1\>Baked Salmon\</h1\>

\</div\>

\</body\>

Anything related to rendering elements to the DOM is found in the
ReactDOM package.

In versions of React earlier than React 16, you could only render one
element to the DOM. Today, it’s possible to render arrays as well.

const dish = React.createElement("h1",  null,  "Baked Salmon");

const dessert = React.createElement("h2",  null,  "Coconut Cream Pie");

ReactDOM.render(\[dish,  dessert\], document.getElementById("root"));

This will render both of these elements as siblings inside of the root
container.

**How to use props.children.**

Children

React renders child elements using props.children. In the previous
section, we rendered a text element as a child of the h1 element, and
thus props.children was set to Baked Salmon.

We could render other React elements as children too, creating a tree of
elements.

The tree has one root element from which many branches grow.

**Example:**

consider the unordered list that contains ingredients:

\<ul\>

\<li\>2 lb salmon\</li\>

\<li\>5 sprigs fresh rosemary\</li\>

\<li\>2 tablespoons olive oil\</li\>

\<li\>2 small lemons\</li\>

\<li\>1 teaspoon kosher salt\</li\>

\<li\>4 cloves of chopped garlic\</li\>

\</ul\>

the unordered list is the root element, and it has six children.

We can represent this ul and its children with React.createElement:

  

React.createElement(

"ul",

null,

React.createElement("li",  null,  "2 lb salmon"),

React.createElement("li",  null,  "5 sprigs fresh rosemary"),

React.createElement("li",  null,  "2 tablespoons olive oil"),

React.createElement("li",  null,  "2 small lemons"),

React.createElement("li",  null,  "1 teaspoon kosher salt"),

React.createElement("li",  null,  "4 cloves of chopped garlic")

);

Every additional argument sent to the createElement function is another
child element.

React creates an array of these child elements and sets the value of
props.children to that array.

Inspect the resulting React element, we would see each list item
represented by a React element and added to an array called
props.children.

If you console log this element:

const list = React.createElement(

"ul",

null,

React.createElement("li",  null,  "2 lb salmon"),

React.createElement("li",  null,  "5 sprigs fresh rosemary"),

React.createElement("li",  null,  "2 tablespoons olive oil"),

React.createElement("li",  null,  "2 small lemons"),

React.createElement("li",  null,  "1 teaspoon kosher salt"),

React.createElement("li",  null,  "4 cloves of chopped garlic")

);

console.log(list);

The result will look like this:

{

"type": "ul",

"props": {

"children": \[

{  "type": "li",  "props": {  "children": "2 lb salmon" }  …    },

{  "type": "li",  "props": {  "children": "5 sprigs fresh rosemary"} 
…    },

{  "type": "li",  "props": {  "children": "2 tablespoons olive oil" } 
…    },

{  "type": "li",  "props": {  "children": "2 small lemons"}  …    },

{  "type": "li",  "props": {  "children": "1 teaspoon kosher salt"} 
…    },

{  "type": "li",  "props": {  "children": "4 cloves of chopped garlic"} 
…    }

\]

...

}

}

each list item is a child

To create this using React, we’ll use a series of createElement calls:

React.createElement(

"section",

{  id: "baked-salmon" },

React.createElement("h1",  null,  "Baked Salmon"),

React.createElement(

"ul",

{  className: "ingredients" },

React.createElement("li",  null,  "2 lb salmon"),

React.createElement("li",  null,  "5 sprigs fresh rosemary"),

React.createElement("li",  null,  "2 tablespoons olive oil"),

React.createElement("li",  null,  "2 small lemons"),

React.createElement("li",  null,  "1 teaspoon kosher salt"),

React.createElement("li",  null,  "4 cloves of chopped garlic")

),

React.createElement(

"section",

{  className: "instructions" },

React.createElement("h2",  null,  "Cooking Instructions"),

React.createElement("p",  null,  "Preheat the oven to 375 degrees."),

React.createElement("p",  null,  "Lightly coat aluminum foil with
oil."),

React.createElement("p",  null,  "Place salmon on foil."),

React.createElement(

"p",

null,

"Cover with rosemary, sliced lemons, chopped garlic."

),

React.createElement(

"p",

null,"Bake for 15-20 minutes until cooked through."

),

React.createElement("p", null, "Remove from oven.")

)

);

**CLASSNAME IN REACT**

Any element that has an HTML class attribute is using className for that
property instead of class.

Since class is a reserved word in JavaScript, we have to use className
to define the class attribute of an HTML element.

This sample is what pure React looks like. Pure React is ultimately what
runs in the browser.

A React app is a tree of React elements all stemming from a single root
element.

React elements are the instructions that React will use to build a UI in
the browser.

# \>CONSTRUCTING ELEMENTS WITH DATA  

**CONSTRUCTING ELEMENTS WITH DATA**

The major advantage of using React is its ability to separate data from
UI elements.

Since React is just JavaScript, we can add JavaScript logic to help us
build the React component tree.

For example, ingredients can be stored in an array, and we can map that
array to the React elements.

# Example:  

Example:

the unordered list

React.createElement(

"ul",

null,

React.createElement("li",  null,  "2 lb salmon"),

React.createElement("li",  null,  "5 sprigs fresh rosemary"),

React.createElement("li",  null,  "2 tablespoons olive oil"),

React.createElement("li",  null,  "2 small lemons"),

React.createElement("li",  null,  "1 teaspoon kosher salt"),

React.createElement("li",  null,  "4 cloves of chopped garlic")

);

The data used in this list of ingredients can be easily represented
using a JavaScript array:

const items = \[

"2 lb salmon",

"5 sprigs fresh rosemary",

"2 tablespoons olive oil",

"2 small lemons",

"1 teaspoon kosher salt",

"4 cloves of chopped garlic"

\];

We want to use this data to generate the correct number of list items
without having to hard code each one.

We can map over the array and create list items for as many ingredients
as there are:

  

React.createElement("ul",

{  className: "ingredients" },

items.map(ingredient =\> React.createElement("li", null, ingredient))

);

This syntax creates a React element for each ingredient in the array.

Each string is displayed in the list item’s children as text.

The value for each ingredient is displayed as the list item.

When running this code, you’ll see a console warning   

<img src="image_20230818063355.png" style="max-width: 100%;"
data-d2l-editor-default-img-style="true" />

When we build a list of child elements by iterating through an array,

React likes each of those elements to have a key property. The key
property is used by React to help it update the DOM efficiently.

You can make this warning go away by adding a unique key property to
each of the list item elements.

We can use the array index for each ingredient as that unique value:

React.createElement(

"ul",

{  className: "ingredients" },

items.map((ingredient,  i)  =\>

React.createElement("li",  {  key: i },  ingredient)

)

);

adding this to each list item will clear the console warning.

**Adjusted code**

\<!DOCTYPE html\>

\<html\>

\<head\>

\<meta charset="utf-8" /\>

\<title\>React Samples\</title\>

\</head\>

\<body\>

  \<!-- Target container --\>

  \<div id="root"\>\</div\>

  
  \<!-- React library & ReactDOM (Development Version) --\>

  \<script
src="<https://unpkg.com/react@16.8.6/umd/react.development.js>"\>\</script\>

  \<script
src="<https://unpkg.com/react-dom@16.8.6/umd/react-dom.development.js>"\>\</script\>

  
  \<script\>

    const items = \[

      "2 lb salmon",

      "5 sprigs fresh rosemary",

      "2 tablespoons olive oil",

      "2 small lemons",

      "1 teaspoon kosher salt",

      "4 cloves of chopped garlic"

    \];

  
    const list = React.createElement(

      "ul",

      { className: "ingredients" },

      items.map((ingredient, i) =\>

        React.createElement("li", { key: i }, ingredient)

      )

    );

  
    ReactDOM.render(list, document.getElementById("root"));

  \</script\>

\</body\>

\</html\>

**Output in the Browser**

<img src="image_20230818063355.png" style="max-width: 100%;"
data-d2l-editor-default-img-style="true" />

## Learning Activity

Read the content related to this learning outcome **and describe how
react works also complete the practical as described in the lecture
slides .**

# References

Chapter 4:Learning React, 2nd Edition by Alex Banks, Eve Porcello
Publisher: O'Reilly Media, Inc. Release Date: June 2020ISBN:
9781492051725; page 64-72/p\>

**COMP-229: Web Application Development**
