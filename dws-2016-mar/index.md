##Darwin Web Standards

###Wed 9/03/2016

[meetup.com/DarwinWebStandards](http://www.meetup.com/DarwinWebStandards/)

[twitter.com/dwebstandards](https://twitter.com/dwebstandards)

Slides available at [slides.darwinwebstandards.org](http://slides.darwinwebstandards.org/)



##Thanks To

* **Matt** and **CDU's Innovative Media Production Studio** for organising the use of this room and facilities.

* **Dash** for providing the drinks and esky for tonight.



##CSS media quries for enhancing print

by [Jonathan Haslett](https://twitter.com/jonathanhaslett)


* @media queries are often used to target specific styles to *media features* wich as *width*, *orientation*, *hover*, and many more.

* We can also use media queries to target *media types* such as *screen*, *print*, or *speech*.

* Let's take a look at some basic styles that can be used to enhance the print output of any content focused web page.


index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Print Demo</title>
  <link rel="stylesheet" href="main.css">
</head>
<body>
  <section>
    <h1>A super basic example web page</h1>
    <p>Here's a really basic web page with a heading, some text, and an image. Use your dev tools to take a look at the print styles and play around with it.</p>
    <p>Here's a <a href="http://slides.jon.haslett.id.au/dws-2016-mar/">link</a> to this month's matching slides, and here it is again as a relative <a href="../">link</a>.</p>
    <p>Here's some more example links:
      <ul>
        <li><a href="https://google.com/">Google</a></li>
        <li><a href="http://meetup.com/">Meetup</a></li>
        <li><a href="http://lab.hakim.se/reveal-js/#/">Reveal.js</a></li>
      </ul>
    </p>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit.</p>
    <img src="image.jpg" alt="Jonathan Haslett" title="Jonathan Approves This Message">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur nam ab repellendus eos, voluptatum consequatur debitis. Eligendi praesentium nemo mollitia! Assumenda eum fugit vitae eveniet maiores! Cumque maxime expedita fugit.</p>
  </section>
</body>
</html>
```


main.css
```css

body{
  background-color: #222222;
  color: #ffffff;
  font-family: sans-serif;
}

section{
  max-width: 800px;
  margin:auto;
}

img{
  max-width: 100%;
}

a{
  color: #f300f3;
}

/*print media query*/
@media only print{
  
  body{
    background-color: #ffffff;
    color: #222222;
  }
  
  section{
    max-width: 90%;
  }

  img{
    max-width: 200px;
    opacity: .75;
  }

  a\[href^="http"\]:after{
    content:" <" attr(href) "> ";
    font-style: italic;
  }

  p,li,img,h1,h2,h3,h4,h5,h6,aside,blockquote{
    page-break-inside:avoid;
  }
}
```


##Demo Site

Use your browsers developement tools to play around with the demo site [here](demo/).



##Darwin Web Standards

* Meetup: [meetup.com/DarwinWebStandards](http://www.meetup.com/DarwinWebStandards/)

* Twitter: [twitter.com/dwebstandards](https://twitter.com/dwebstandards)

* Email: [darwinwebstandards@gmail.com](mailto:darwinwebstandards@gmail.com)