# CSS-Explained
##Intro
- IS

- DOES
- BROWSER SUPPORT

##BASIC SYNTAX

##TRANSITION

```css
a {
	color: red;
}

a:hover {
	color: yellow;
}
```
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

Enables the transitions of properties from one state to the next over a defined length of time.

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
They are working towards making everything transitionable, but at the moment anything that has intermediate values can be transitioned. In this example code opacity: 1 and code opacity: 0 the midpoint would be 0.5. In code halfway, :halfway is not a real psudeo element it was used for this example. There is no midway point between display: block and display: none.

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
