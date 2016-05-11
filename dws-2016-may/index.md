##Darwin Web Standards

###Wed 11/05/2016

[meetup.com/DarwinWebStandards](http://www.meetup.com/DarwinWebStandards/)

[twitter.com/dwebstandards](https://twitter.com/dwebstandards)

[slides.darwinwebstandards.org](http://slides.darwinwebstandards.org/)



##Thanks To

* [Charles Darwin University](http://cdu.edu.au/) for providing the room and facilities.



##Better Web Font Loading

by [Jonathan Haslett](https://twitter.com/jonathanhaslett)

Jon is a co-founder of [Dash](https://dash.marketing/), a Darwin based web design and digital marketing company. As a web front-end development nerd, Jon regularly gets obsessed with finding new and better ways to solve old problems using the latest tools, processes, and web standards. He also likes to travel and listen to podcasts.

###Additional Resources

* Jon's Demo [Page 1](demo/1) and [Page 2](demo/2)

* [Web Font Loader on **github**](https://github.com/typekit/webfontloader)


##Web Fonts Today

The ability to load custom web fonts is now a fact of life: 
* Designers expect it
* Font foundries embrace it
* Third party platforms make lisncing and distribution easy


##Popular Font Platforms

* [Google Fonts](https://www.google.com/fonts)
* [Typekit](https://typekit.com/) (by Adobe)
* [Fonts.com](https://www.fonts.com/)
* [Fontdeck](http://fontdeck.com/)


##Problems

* Not all fonts are available from all platforms, it's possible for a website design in incorporate fonts from multiple platforms in a single project.

* Some fonts arent on third part platforms and are loaded from your own web server.

* **Resource blocking**. The additional CSS and Javascript files used to load fonts along with the standard instructions provided by vendors can often hold up the initial rendering of the page. This makes the site feel slow to load.

* The dreaded **Flash of Unstyled Text (FOUT)** where fallback fonts are displayed while the correct font is still downloading and being applied.


##A Possible Solution

[Web Font Loader](https://github.com/typekit/webfontloader) is an open sourced project co-developed by [Google](https://www.google.com/fonts) and Adobe's [Typekit](https://typekit.com/).

It provides a common interface for anyncronous font loading regardless of the source. It also adds a standard set of events you may use to control the loading experience.

In theory it should help mitigate all of the problems identified above regardless of where our fonts come from.


##Let's take a look
Demo time (yay!)

[Page 1](demo/1) and [Page 2](demo/2)


index.html - without Web Font Loader
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Demo 1 - No WebFontLoader</title>
  
  <link rel="stylesheet" href="main.css">

  <!-- google fonts -->
  <link href="https://fonts.googleapis.com/css?family=Indie+Flower" rel="stylesheet">

  <!-- font hosted on this web server -->
  <link rel="stylesheet" href="fonts.css">

  <!-- typekit -->
  <script src="https://use.typekit.net/dvc5fkn.js"></script>
  <script>try{Typekit.load({ async: true });}catch(e){}</script>

</head>
<body>
  <main>
    <h1>Example without Web Font Loader [from typekit]</h1>
    <p>In this example, wer'e loading and styling three different fonts, one each from Typekit, Google Fonts, and this web server which is hosted by Github. [from google fonts]</p>
    <p>The idea is that you'll use dev tools to inspect your network requests and take a look at how much worse this version is compared to the second example. [from the local server, loaded with @font-face css]</p>

    <h2>Demo Navigation</h2>
    <ul>
      <li><a href="../1">Without Web Font Loader</a></li>
      <li><a href="../2">With Web Font Loader</a></li>
    </ul>
  </main>
</body>
</html>
```


index.html - with Web Font Loader and Modernizr
```html
<!DOCTYPE html>
<html lang="en" class="no-js wf-loading">
<head>
  <meta charset="UTF-8">
  <title>Demo 2 - WebFontLoader</title>
  
  <!-- use modernizr so that we have a robust way for CSS to detect if JavaScript is running -->
  <script>
  /*! modernizr 3.3.1 (Custom Build) | MIT *
   * http://modernizr.com/download/?-setclasses !*/
  !function(n,e,s){function o(n,e){return typeof n===e}function a(){var n,e,s,a,i,l,r;for(var c in f)if(f.hasOwnProperty(c)){if(n=[],e=f[c],e.name&&(n.push(e.name.toLowerCase()),e.options&&e.options.aliases&&e.options.aliases.length))for(s=0;s<e.options.aliases.length;s++)n.push(e.options.aliases[s].toLowerCase());for(a=o(e.fn,"function")?e.fn():e.fn,i=0;i<n.length;i++)l=n[i],r=l.split("."),1===r.length?Modernizr[r[0]]=a:(!Modernizr[r[0]]||Modernizr[r[0]]instanceof Boolean||(Modernizr[r[0]]=new Boolean(Modernizr[r[0]])),Modernizr[r[0]][r[1]]=a),t.push((a?"":"no-")+r.join("-"))}}function i(n){var e=r.className,s=Modernizr._config.classPrefix||"";if(c&&(e=e.baseVal),Modernizr._config.enableJSClass){var o=new RegExp("(^|\\s)"+s+"no-js(\\s|$)");e=e.replace(o,"$1"+s+"js$2")}Modernizr._config.enableClasses&&(e+=" "+s+n.join(" "+s),c?r.className.baseVal=e:r.className=e)}var t=[],f=[],l={_version:"3.3.1",_config:{classPrefix:"",enableClasses:!0,enableJSClass:!0,usePrefixes:!0},_q:[],on:function(n,e){var s=this;setTimeout(function(){e(s[n])},0)},addTest:function(n,e,s){f.push({name:n,fn:e,options:s})},addAsyncTest:function(n){f.push({name:null,fn:n})}},Modernizr=function(){};Modernizr.prototype=l,Modernizr=new Modernizr;var r=e.documentElement,c="svg"===r.nodeName.toLowerCase();a(),i(t),delete l.addTest,delete l.addAsyncTest;for(var u=0;u<Modernizr._q.length;u++)Modernizr._q[u]();n.Modernizr=Modernizr}(window,document);
  </script>

  <!-- using Web Font Loader instead -->
  <script>
     WebFontConfig = {
        typekit: { id: 'dvc5fkn' },
        google: { families: ['Indie Flower'] },
        custom: {
            families: ['chunkfiveroman'],
            urls: ['fonts.css']
          },
        timeout: 10000 // Set the timeout to two seconds
     };

     (function(d) {
        var wf = d.createElement('script'), s = d.scripts[0];
        wf.src = 'https://ajax.googleapis.com/ajax/libs/webfont/1.6.16/webfont.js';
        s.parentNode.insertBefore(wf, s);
     })(document);
  </script>

  <link rel="stylesheet" href="main.css">

</head>
<body>
  <main>
    <h1>Example with Web Font Loader [from typekit]</h1>
    <p>In this example, wer'e loading and styling three different fonts, one each from Typekit, Google Fonts, and this web server which is hosted by Github. [from google fonts]</p>
    <p>The idea is that you'll use dev tools to inspect your network requests and take a look at how much worse this version is compared to the second example. [from the local server, loaded with @font-face css]</p>

    <h2>Demo Navigation</h2>
    <ul>
      <li><a href="../1">Without Web Font Loader</a></li>
      <li><a href="../2">With Web Font Loader</a></li>
    </ul>
  </main>
</body>
</html>
```


main.css - without Web Font Loader
```css
body{
  max-width: 700px;
  margin: auto;
}

main{
  background: #e2e2e2;
  padding: 10px 20px 20px 20px;
}

h1,h2 {
  font-family: "blenny",sans-serif;
  font-size: 60px;
  line-height: 65px;
  }

h1 {
  font-size: 60px;
  line-height: 65px;
  }

h2 {
  font-size: 30px;
  line-height: 35px;
  }

p:nth-child(2n),
li{
  font-family: 'Indie Flower', sans-serif;
  font-size: 20px;
}

p:nth-child(2n+1){
  font-family: 'chunkfiveroman', sans-serif;
  font-size: 20px;
}
```


main.css - with Web Font Loader
```css
body{
  max-width: 700px;
  margin: auto;
}

main{
  background: #e2e2e2;
  padding: 10px 20px 20px 20px;
}

h1,h2 {
  font-family: "blenny",sans-serif;
  font-size: 60px;
  line-height: 65px;
  }

h1 {
  font-size: 60px;
  line-height: 65px;
  }

h2 {
  font-size: 30px;
  line-height: 35px;
  }

p:nth-child(2n),
li
{
  font-family: 'Indie Flower', sans-serif;
  font-size: 20px;
  line-height: 25px;
}

p:nth-child(2n+1){
  font-family: 'chunkfiveroman', sans-serif;
  font-size: 20px;
  line-height: 25px;
}

html.js.wf-loading h1,
html.js.wf-loading h2,
html.js.wf-loading p,
html.js.wf-loading li{
  visibility: hidden;
}
```


fonts.css - same file used in both versions
```css
/*load the locally hosted font familiy ready for use*/
@font-face {
    font-family: 'chunkfiveroman';
    src: url('chunkfive-webfont.woff2') format('woff2'),
         url('chunkfive-webfont.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}
```


##The Results

* One unified interface
* No more FOUT
* Fallback fonts still work if needed



##Darwin Web Standards

* Meetup: [meetup.com/DarwinWebStandards](http://www.meetup.com/DarwinWebStandards/)

* Twitter: [twitter.com/dwebstandards](https://twitter.com/dwebstandards)

* Email: [darwinwebstandards@gmail.com](mailto:darwinwebstandards@gmail.com)