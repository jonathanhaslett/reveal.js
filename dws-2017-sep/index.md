## Darwin Web Standards

### Wed 13/09/2017



## We've got a Slack
Join us at:
https://slack.darwinwebstandards.org



## Shout-out to:

* [Charles Darwin University](http://cdu.edu.au/) for providing the room and facilities.

* [Dash](https://dash.marketing) for paying the Meetup.com fees.



## Getting started with Flexbox

by [Jon Haslett](https://twitter.com/jonathanhaslett)


## 20 years of float

Since the early days of CSS ([Cascading Style Sheets, level 1 - W3C Recommendation 17 Dec 1996](https://www.w3.org/TR/CSS1/#float)) we have used combinations of ```display:``` and ```float:``` to achieve complex layouts for our interfaces and content.

```css
.item{
  display:block;
  float:left;
}
```

Floats are a hack. They were designed to 'float' and image so that text coudl flow around it to replicate popular magazine and newspaper print layouts ([demo](https://codepen.io/jacobfentress/pen/LbmIc)).


## Enter Flexbox

The Flexible Box Layout Module Level 1 became a [W3C Candidate Recommendation on 26 May 2016](https://www.w3.org/TR/css-flexbox-1/).

In September 2017 the latest versions of all browsers support the new standard ([Can I use flexbox](https://caniuse.com/#feat=flexbox)).


## But what is it?

Flex is a new rendering box type for the ```display:``` property that sits alongside other [options](https://developer.mozilla.org/en-US/docs/Web/CSS/display) such as:

```css
.container{
  display:block;
  display:inline;
  display:table;
}
```
Instead we can write:

```css
.container{
  display:flex;
}
```


## Why?

```display:flex;``` opens up a range of new CSS properties for both the container element and it's children.


## On the container

```css
.container{
  display:flex;

  /* Set the main-axis that children should flow */
  flex-direction: row | row-reverse | column | column-reverse;

  /* Should children squeeze into one row or wrap to a new line? */
  flex-wrap: nowrap | wrap | wrap-reverse;

  /* Shorthand that combines flex-direction and flex-wrap */
  flex-flow: <'flex-direction'> || <'flex-wrap'>;

  /* Defines the alignment along the main axis. */
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;

  /* How should items be laid out along the axis on the current line? */
  align-items: flex-start | flex-end | center | baseline | stretch;

  /* When there are multiple lines of items, how are those lines positioned */ within the container?
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;

}
```


## On the items

```css
.item {

  /* Manually specify the sort order for items rather than using the markup order */
  order: <integer>;

  /* Override the alignment specified by align-items*/
  align-self: auto | flex-start | flex-end | center | baseline | stretch;

  /* When there is free space, how should we distribute the growth of element to take up the extra space? */
  flex-grow: <number>; /* default 0 */

  /* If there's not enough space, how should we distribute the shrinking of elements? */
  flex-shrink: <number>; /* default 1 */

  /* Define the default size of an element before the remaining space is distributed. */
  flex-basis: <length> | auto; /* default auto */

  /* Shorthand for flex-grow, flex-shrink, and flex-basis*/
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]

}
```


## Super heaps fun demo

https://codepen.io/enxaneta/pen/adLPwv

As you'll see, there are many possibilities that were either very difficult or impossible to achieve in the past with CSS alone.


## Things we've learnt

* Combine advanced selectors and @media queries to achieve things that were previously only possible using Javascript.

* Ideal for achieving complex responsive layouts and modular components.

* Can be tedious as a replacement for a grid system. Don't worry, were gong to get the [CSS Grid Layout Module](https://www.w3.org/TR/css3-grid-layout/) for that.


## Questions


## Links

https://css-tricks.com/snippets/css/a-guide-to-flexbox/

https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties#toc-flex-grow

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes

https://medium.freecodecamp.org/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af

https://codepen.io/enxaneta/pen/adLPwv



## Darwin Web Standards

* Slack: [slack.darwinwebstandards.org](https://slack.darwinwebstandards.org)

* Meetup: [meetup.com/DarwinWebStandards](http://www.meetup.com/DarwinWebStandards/)

* Twitter: [twitter.com/dwebstandards](https://twitter.com/dwebstandards)

* Email: [darwinwebstandards@gmail.com](mailto:darwinwebstandards@gmail.com)
