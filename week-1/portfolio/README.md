# Portfolio Page

<b>Today we'll cover some of the basics of HTML, CSS, and Javascript by building out a portfolio page!</b>
The end result will look something like the below:

<img /> 

To minimize setup on your personal computer, we'll use an online editor called codepen. Click this <a href='https://codepen.io/'>link<a/> and on the far left pane,
click the <b>Pen</b> dropdown and click on the first option <b>Pen</b> to create your new project. You should see three tabs for <b>HTML</b>, <b>CSS</b> and <b>JS</b> 
for JavaScript. Let's have a brief overview of what these three technologies are and help you accomplish.

## Technologies we'll be using
- <b>HTML</b> - for creating the structure of our page.  
Stands for "Hyper Text Markup Language".  
Describes the structure of a Web page and is the standard "markup" language for web pages.  
Consists of HTML "elements" ex: h1 for heading 1, or p for paragraph. 
- <b>CSS</b> - To "style" our HTML "elements".  
Stands for Cascading Style Sheets.  
Describes how HTML elements are to be displayed    
- <b>JavaScript</b> - to create interaction by updating and changing both our HTML and CSS.  
The (main) Programming Language for the Web.  
Can update and change HTML and CSS.  
Can calculate, manipulate and validate data.  

### Base HTML
Let's start off by pasting in the below HTML code snippet. This will create the skeleton if you will for our page.
```HTML
<!-- This line is a "comment" in HTML. It will not be read by the browser. -->
<!DOCTYPE html> <!-- This tag is standard. It tells the browser that this is a "html" "document" -->
<html> <!-- Beginning of HTML -->
  <head> 
    <title>Title of the document</title>
  </head>

  <body>
    The content of the document......
  </body>

</html> <!-- End of HTML -->
```

We'll want to add in some elements to create the layout of our page: 
- Inside the <b>body</b> opening and closing tags, add in a `<nav>` element for the navigation bar. Don't forget the closing tag (`</nav>`)!  
Type in "Navigation" in between the opening and closing <b>nav</b> tags for now.
- On 3 separate lines, also add in 3 different <b>section</b> elements (<b>always</b> opening and closing: <section></section>).  
Those will be for the "About", "Projects" and "Contact" sections. Type those in between each tag for now.

The body of your html should look something like this: 
```HTML 
...
  <body>
    <nav>Navigation</nav>
    <section>About</section>
    <section>Projects</section>
    <section>Contact</section>
  </body>
...
```

Great! Now let's build out our Navigation bar! 
## Navigation bar

### Navigation HTML `<nav></nav>`
- Let's delete the text we added in between the <b>nav</b> elements. Move the closing tag to the next line.  
- In between the two `<nav>` tags, let's create an "<b>Unordered List</b>" with the `<ul></ul>` element.  
- Inside the `<ul>` let's add in three <b>list items</b> (`<li>`s) for About, Projects, and Contact.  
- For each <b>list item</b>, add in an <b>anchor</b> tag with an <b>`href` property </b>: `<a href=""></a>`.  
Anchor tags are links, and href specifies where to link to.  
- In between each <b>anchor</b> tag, type in About, Projects, and Contact Respectively.  

Your nav should now have the following structure:
```HTML
...
  <nav>
    <ul>
      <li>
        <a href="">About</a>  
       </li>
      <li>
        <a href="">Projects</a>
      </li>
      <li>
        <a href="">Contact<a>
      </li>
    </ul>
  </nav>
...
```

<i>"Okay Kevin, that's great - but this is just... Ugly."</i>  
I'm glad you mentioned it, I was thinking the same thing. Should we at least add some styles to the navbar? I think so too. Let's do it!

### CSS for the Nav bar

Before we jump into the CSS for the nav, let's add some <b>id</b>s and <b>classes</b> to our nav elements so we can reference them in the CSS.
- Add a <b>class property</b> of value "nav" to the opening `<nav>` tag: `<nav class="nav">`
- Add a <b>class property</b> pf value "nav-list" to the opening `<ul>` tag: `<ul class="nav-list">`

Now to CSS!
Before we start styling our nav bar, let's add in some CSS <b>variables</b> for colors that we can reuse. We'll also remove the extra whitespace that is there by default.
Paste in the below at the top of your CSS tab.
```CSS
/* CSS */
/* Custom properties/variables  */
:root {
  --main-white: #f0f0f0;
  --main-red: #be3144;
  --main-blue: #45567d;
  --main-gray: #303841;
}

/* Base reset for whitespace */
* {
  margin: 0;
  padding: 0;
}
```

To target the <b>classes</b> we added to the `nav` and `ul`, we just prefix them with a ".". We can also target HTML <b>elements</b> directly, specified by their parent classes.
In your css tab. Add the following:
```CSS
.nav {

}
.nav .nav-list {

}
.nav .nav-list li {

}
.nav .nav-list li a {

}
```

Awesome. Now let's lay out our nav. I'll talk us through what this code does. I suggest typing them in one by one to see how it impacts your page at each step :).
```CSS
.nav {
  display: flex; 
  justify-content: flex-end;
  background-color: var(--main-red); /* Our variable for our red color */
  padding: 20px 25px; /* "20px of padding on the top and bottom, 25px on the left and right" */
}

.nav .nav-list {
  list-style: none; /* removes the bullet points */
  display: flex; 
}

.nav .nav-list li {
    margin-left: 20px; /* 20px of space to the left of the element */
}

.nav .nav-list li a {
  font-size: 24px; 
  text-decoration: none;
  color: var(--main-white); /* Our variable for our white color */
}
```


Great! Much better! Now because we're fancy, let's make the links change color to the blueish variable we added when we hover over them.
```CSS
.nav .nav-list li a:hover {
  color: var(--main-blue); /* Our variable for our blue color */
}
```

Beautiful. Now let's switch back to HTML and add in content for the About Section. We'll keep this rather simple.

## About Section

### HTML for the About Section
- Add an `id` <b>property</b> of value "about" as well as a `class` <b>property</b> of "section about" to the opening `section`tag:  
`<section id="about" class="section about">`
- Inside the about `section` tag. Add an `h1` tag, a "self-closing" `img` tag with an `alt` <b>property</b> and `src` <b>property</b>, as well as a `p` tag. 
- Give the `img` `alt` property a `value` of "Profile picture" and give the `src` property a value of "https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"

Your about section will look like the below:
```HTML
...
  <section id="about" class="section about"> <!-- Start About -->
      <h1>Hi, my name is Kevin</h1>
      <img alt="Profile pic" src="https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"/>
      <p>I'm a Frontend Engineer at Paperspace!</a>
  </section> <!-- END About -->
...
```
