# CSS-Explained
##Intro
- IS
- DOES
- BROWSER SUPPORT

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
