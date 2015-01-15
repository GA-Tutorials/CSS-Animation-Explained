![](https://github.com/mrbernz/CSS-Animation-Explained/blob/master/animaniacs.png "CSS Animaniacs")
# CSS3-Explained

##Intro

CSS3 has been split into "modules". It contains the "old CSS specification" (which has been split into smaller pieces). In addition, new modules are added. This also allows the browser to support sections of the specification but keep their code block to a minimum by only supporting those modules that make sense. Some of the CSS3 modules are:

Selectors
- Box Model
- Backgrounds and Borders
- Image Values and Replaced Content
- Text Effects
- 2D/3D Transformations
- Animations
- Multiple Column Layout
- User Interface

What is interesting about selectors is they allow designers/developers to select on much more specific levels of the document.

###BROWSER SUPPORT

- webkit-animation: NAME-YOUR-ANIMATION 5s infinite; /* Safari 4+ */
- moz-animation:    NAME-YOUR-ANIMATION 5s infinite; /* Fx 5+ */
- o-animation:      NAME-YOUR-ANIMATION 5s infinite; /* Opera 12+ */
- animation:         NAME-YOUR-ANIMATION 5s infinite; /* IE 10+, Fx 29+ */


##BASIC SYNTAX

###Shorthand Notation
You can call the animation event on any html element as a css property - just as if you were changing the background color.

```css

  .element-to-animate {
    animation: your-animation 1s 2s 3 alternate backwards;
  }

```
The shorthand above has the following values: name of the animation, duration, delay, duration count, fill-mode, and direction (Check for a table of options below).

You can then use keyframes (think of a timeline) to change different css characteristics at various times.

```css
@keyframes you-animation {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}

```
So, at at the start of the animation, the opacity of your element will be 0, and at 100% completion, your element will have an opacity of 1.

###Vendor Prefixes

Unfortunately browser support isn't great at this time, so don't forget to include the following vendor prefixes for your keyframe declaration as well as when calling the animation on the elements.

```css
@-webkit-keyframes NAME-YOUR-ANIMATION {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}
@-moz-keyframes NAME-YOUR-ANIMATION {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}
@-o-keyframes NAME-YOUR-ANIMATION {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}
@keyframes NAME-YOUR-ANIMATION {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}
```

```css
#box {
  -webkit-animation: NAME-YOUR-ANIMATION 5s infinite;
  -moz-animation:    NAME-YOUR-ANIMATION 5s infinite;
  -o-animation:      NAME-YOUR-ANIMATION 5s infinite;
  animation:         NAME-YOUR-ANIMATION 5s infinite;
}
```

###Options

| timing-function   |  duration & delay | duration-count   | fill count     |animation-direction   |
|---|---|---|---|---|
| ease, ease-out, ease-in, ease-in-out, linear, cubic-bezier(x1, y1, x2, y2) (e.g. cubic-bezier(0.5, 0.2, 0.3, 1.0))  |  Xs or Xms |  X | forwards, backwards, both, none  |  normal, alternate |


##TRANSITION

```css
a {
	color: red;
}

a:hover {
	color: yellow;
}
```
For example, if you change the color of an element from red to yellow, usually the change is instantaneous.
```css
a {
	color: red;
	transition: 1s;
}

a:hover {
	color: yellow;
}
```
This is a transition done over one second. We are changing a property, in this case the color property over an amount time. 

CSS transitions, which are part of the CSS3 set of specifications, provide a way to control animation speed when changing CSS properties. Instead of having property changes take effect immediately, you can cause the changes in a property to take place over a period of time.

The transitions of properties changes from one state to the next over a defined length of time.

- transition-property: properties (or 'all') that transition
- transition-duration: s or ms it takes to transition
- transition-timing-function: bezier curve to transition
- transition-delay: s or ms before transition starts
- transition: shorthand for 4 transition properties

###What can be transitioned?

```css
code {
	opacity: 1;
}
code:halfway {
	opacity: 0.5;
} 
code:hover {
	opacity:0;
}
```
```css
code {
	display: block;
}
code:halfway {
	display: ???
}
code:hover {
	display: none;
}
```
Eventually the idea is to make everything transitionable, but at the moment anything that has intermediate values can be transitioned. In this example code opacity: 1 and code opacity: 0 the midpoint would be 0.5. In code halfway, :halfway is not a real psudeo element it was used for this example. There is no midway point between display: block and display: none.

###Two values that have REAL intermediary values
```css
code {
	font-size: 100%;
}
code:halfway {
	font-size: 110%;
}
code:hover {
	font-size: 120%;
}
```

```css
code {
	height: auto;
}
code:halfway {
	height: ???
}
code:hover {
	height: 1000px;
}
```
Above font-size: 100% and font-size: 120%, the midpoint would be 110%. There is no mid-way point between height: auto and height: 1000px. The best solution is to set a min-height: 0 and min-height: 1000px.

###Transitionable Poperties
- background-color
- background-position
- border-color
- border-width
- border-spacing
- bottom
- clip
- color
- crop
- font-size
- font-weight
- height
- left
- letter-spacing 
- line-height
- margin
- max-height
- min-height
- min-width
- opacity
- outline-color
- outline-offset
- outline-width
- padding
- right
- text-indent
- text-shadow
- top
- vertical-align
- visibility
- width
- word-spacing
- z-index

These all have a midpoints except visibility. So what happens to visibility is right before it reaches 100% it switches to the value.

###Transition Features (or Limitations)
- Single Iteration
	+ You have not control over
	+ It goes from keyframe 0 to keyframe 100 and you can't tell it what to do in between
- Reverse goes to initial state 
- No granualr control
- Limited methods of initiation
- Can't force them to finish

##ANIMATION

The animation shorthand property is a comma-separated list of animation definitions. Each item in the list gives one item of the value for all of the subproperties of the shorthand, which are known as the animation properties. (See the definition of animation-name for what happens when these properties have lists of different lengths, a problem that cannot occur when they are defined using only the animation shorthand.

### List of Animation Properties

- @keyframes	Specifies the animation	3
- animation	A shorthand property for setting all the animation properties, except the animation-play-state and the - animation-fill-mode property	3
- animation-delay	Specifies when the animation will start	3
- animation-direction	Specifies whether or not the animation should play in reverse on alternate cycles	3
- animation-duration	Specifies how many seconds or milliseconds an animation takes to complete one cycle	3
- animation-fill-mode	Specifies what styles will apply for the element when the animation is not playing (when it is  finished, or when it has a "delay")	3
- animation-iteration-count	Specifies the number of times an animation should be played	3
- animation-name	Specifies the name of the @keyframes animation	3
- animation-play-state	Specifies whether the animation is running or paused	3
- animation-timing-function	Specifies the speed curve of the animation	3

##SOURCES
- [W3C](http://www.w3.org/TR/css3-animations/)
- [Safari CSS Reference](http://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariCSSRef/Articles/StandardCSSProperties.html#//apple_ref/doc/uid/TP30001266-_webkit_animation)
- [MDN](https://developer.mozilla.org/en/css/css_animations)
- [CSS-Tricks](http://css-tricks.com/almanac/properties/a/animation/)
- [Estelle's Github](estelle.github.io)
- [CSS3 Animation Examples](http://www.creativebloq.com/css3/animation-with-css3-712437)
