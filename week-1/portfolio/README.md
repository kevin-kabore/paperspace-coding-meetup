# Portfolio Page

<b>Today we'll cover some of the basics of HTML, CSS, and Javascript by building out a portfolio page!</b>   
The end result will look something like the below:

![](portfolio-final.gif)

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
Add an `id` <b>property</b> of value "about" as well as a `class` <b>property</b> of "section about" to the opening `section`tag:  
`<section id="about" class="section about">`
Inside the about `section` tag:
1. Add an `h1` tag with text inside "Hi, my name is X"
2. Add an opening and closing `div` with a <b>class name</b> of "profile-pic". 
3. Inside the `div`, add a "self-closing" `img` tag with an `alt` <b>property</b> and `src` <b>property</b>
4. Give the `img` `alt` property a `value` of "Profile picture" and give the `src` property a value of "https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"
5. Add a `p` tag with some text "I'm a web developer now!"

Your about section will look something like this:
```HTML
...
  <section id="about" class="section about"> <!-- Start About -->
      <h1>Hi, my name is Kevin</h1>
      <div class="profile-pic">
        <img alt="Profile pic" src="https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"/>
      </div>
      <p>I'm a Frontend Engineer at Paperspace!</p>
    </section> <!-- END About -->
...
```

We'll use the id property to scroll to when we click on our menu items with a little trick. And we'll use the classes we added for styling purposes. `<div>` stands for "division" and is often used to group related elements similar to the section tag. In this case, we'll use it to set the size of our image.


### CSS for the About Section
Great, Now let's get into some CSS. I'll give you the CSS code snippet and explain it below. I suggesst adding each line one by one and seeing how it affects your section :) 
```CSS
.section {
  padding: 20px 25px;
}

.section.about {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background-color: #000;
  background-image: linear-gradient(to top right, #3a3d40, #181719);
}

.section.about h1 {
  color: var(--main-white);
  font-size: 38px; 
  margin-bottom: 16px;
}

.section.about .profile-pic {
  width: 225px;
  margin: 0 auto;
}

.section.about .profile-pic img {
  width: 100%;
  height: auto;
}

.section.about p {
  font-size: 24px;
  margin-top: 16px;
  color: var(--main-red)
}
```
<b>`.section`</b>  
First we start off by adding some <b>padding</b> of 20px to the top and bottom, and 25px to the left and right of the section. We'll add this class to other sections as well. This gives us some smooth spacing so our elements don't touch the edges of the section.  

<b>`.section.about`</b>   
This targets any elements that have a class of "section" <b>and</b> a class of "about".  
The first four lines are <b><a href="https://css-tricks.com/snippets/css/a-guide-to-flexbox/">CSS flexbox</a></b> properties. 
By line we're: "enabling a <b>flex</b> context for all the direct children of `.section.about`", as a <b>column</b> (default row). We're then going to <b>justify</b> all the content center and align all the items in the center as well.  
Then we'll set a <b>width</b> of 100% so items are truly in the center. We'll also give the about section a <b>height</b> of 100vh meaning 100% of the "view height".  
Lastly we'll give the section a <b>background-color</b> of black, and use a trick to add a linear-gradient "to the top right" using the <b>background-image</b> CSS property. The gradient will go from color `#3a3d40` in bottom left to `#181719` in the top right.

<b>`.section.about h1`</b>  
This references the heading 1 of our about section.  We'll add a <b>color</b> equal to our variable of "--main-white", a font-size and a margin at the bottom.

<b>`.section.about .profile-pic` and `.section.about .profile-pic img`</b>   
This is the `div` that we added for our image. What we're doing here is a common trick to have "responsive" images. Instead of setting the width on the image directly, we'll give it a <b>width</b> of 100% and <b>height</b> of auto. Then use the `div` to set a specific width. `margin: 0 auto` is also a common trick for centering content horizontally.

the styles for the paragraph should be looking a little more familiar now. Just adding some font size, a margin at the top and a color :) 

Beautiful! We're starting to see somewhat of a page here, nice! Onto the projects section!

## Projects

### HTML for the Projects section
Let's add an <b>id</b> of "projects" as well as two <b>classes</b>: "section" and "projects" to our `section`.   
Inside the projects section:   
- let's add an `h1` with a <b>class</b> of "projects-header" and some text "These are some of my projects"
- Add a `div` with a <b>class</b> of "projects-container". We'll use this to contain our cards for all of our projects.

Now, I know we don't have any projects yet - but let's lay this out with some dummy projects for now. 
We'll add 4 "project-cards" to the "projects-container". We'll represent each of them like this, with the same image we used on the profile for now: 
```HTML
...
    <div class="project-card">
      <div class="project-img-container">
        <img alt="project-img" src="https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"/>
      </div>
      <div class="project-title">
        <p>Title</p>
      </div>
    </div>
...
```
Our complete HTML for this section will now look like this:
```HTML
...
    <section id="projects" class="section projects"> <!-- Start Projects -->
      <h1 class="projects-header">These are some of my projects</h1>
      <div class="projects-container"> <!-- Start projects-container -->
        <div class="project-card"> <!-- Start project-card -->
          <div class="project-img-container">
            <img alt="project-img" src="https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"/>
          </div>
          <div class="project-title">
            <p>Title</p>
          </div>
        </div> <!-- END project-card -->
        
        <div class="project-card"> <!-- Start project-card -->
          <div class="project-img-container">
            <img alt="project-img" src="https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"/>
          </div>
          <div class="project-title">
            <p>Title</p>
          </div>
        </div> <!-- END project-card -->
        
        <div class="project-card"> <!-- Start project-card -->
          <div class="project-img-container">
            <img alt="project-img" src="https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"/>
          </div>
          <div class="project-title">
            <p>Title</p>
          </div>
        </div> <!-- END project-card -->
        
        <div class="project-card"> <!-- Start project-card -->
          <div class="project-img-container">
            <img alt="project-img" src="https://cms.ironk12.org/wp-content/uploads/2020/02/no-person-profile-pic.png"/>
          </div> 
          <div class="project-title">
            <p>Title</p>
          </div>
        </div> <!-- END project-card -->
      </div> <!-- END projects-container -->
    </section> <!-- End Projects -->
...
```
Great! Now for some styles!

### CSS for the Projects section

Let's do this piece by piece.   
<b>`.section.projects`</b>  
We know that we want everything centered in the section, a blue background and a little space. So we can use flexbox to get this layout and pass in our color variable plus add in some padding.
We'll add the following to our CSS:
```CSS
.section.projects {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 50px 25px;
  background-color: var(--main-blue);
}
```
<b>`.section.projects .projects-header`</b>  
The header is pretty straight forward. We see that there is a line under the header. We'll use a `border-bottom` CSS <b>property</b> to accomplish this.
We'll also create and use a new variable for the header font size "--h1-font-size" and add this to our `:root` css element. While we're at it, let's add another variable for `p`, and call it `--p-font-size`:

```CSS
:root {
 ...
  --h1-font-size: 38px;
  --p-font-size: 24px;
}
...
...
.section.projects .projects-header {
  color: var(--main-white);
  font-size: var(--h1-font-size);
  margin: 0 auto 40px auto;
  border-bottom: 4px solid var(--main-white);
}
```
<b>`.section.projects .projects-container`</b>  
Let's use flex box again to lay these out and center them:
```CSS
...
.section.projects .projects-container {
  display: flex;
  justify-content: center;
}
```
Now for each project card.  
<b>`.project-card`</b>   
Let's center everything in the card. Get some spacing in between each card with margin, and make sure all the text is our white variable.
```CSS
...
/* Project card styles start */
.project-card {
  text-align: center;
  margin: 0 16px;
  color: var(--main-white);
}
```
Nice. Now let's make the text change color to blue when we hover over a card, and give the user an indication that this will be clickable (in the future):
```CSS
...
.project-card:hover {
  color: var(--main-red);
  cursor: pointer;
}
```
Sweet. Now let's make our image a little bigger by having the div control all the sizing. We'll give the image a `width` of 100% and a `height` of auto:
```CSS
.project-card .project-img-container {
  width: 250px;
}
.project-card .project-img-container img {
  width: 100%;
  height: auto;
}
```
And finally for our project title! Let's create a slightly transparent box to contain this for presentation.  
We'll give this box a half opaque or transparent `background-color`, and add some `padding`.  
We notice there's a tiny bit of space below the image, so we'll move up the text box a few pixels with a negative `margin-top`.  
```CSS
...
.project-card .project-title-container {
  background-color: rgba(0, 0, 0, 0.5);
  padding: 16px 8px;
  margin-top: -5px;
}
```
And finally, give our title a `font-size` equivalent to the `--p-font-size` variable we recently added:
```CSS
.project-card .project-title-container p {
  font-size: var(--p-font-size);
}
```

AWESOMEEEE. We have something that's starting to resemble a web page now!   
But let's do something minor really quickly. Remember our nav how we added in those <b>anchor</b> (`<a>`) tags? Well we also added in some `ids` for each of our sections.   
In the `about` and `projects` <b>anchor</b> `href`, let's add in the id name for each, prefixed by a `#`. This will tell our anchor to go to the id on this page that you specify. We'll also add a link to #contact:
```HTML
...
    <nav class="nav"> <!-- Start Nav --> 
      <ul class="nav-list">
        <li>
          <a href="#about">About</a>  
         </li>
        <li>
          <a href="#projects">Projects</a>
        </li>
        <li>
          <a href="#contact">Contact<a>
        </li>
      </ul>
    </nav> <!-- END Nav -->
...
```
Now try clicking each of the links :)
