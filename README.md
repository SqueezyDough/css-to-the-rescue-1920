# CSS to the Rescue @cmda-minor-web 19-20
In this course I will create an interactive webpage using CSS and HTML only. I will build features that are usually done with javascript.

I will have to pick a context and 2 restrictions as an extra challenge. I will have to think of a workaround which ultimately challenge me to be more creative!

## Learning goals:
- You understand the broader scope of CSS: You can show that CSS can be used for more than just styling web pages.
- You understand the progressive enhancement parts of CSS: You can show that you can use the cascade, inheritance and specificity in your project
- You understand the interactive parts of CSS: Is the UX fully enhanced within in given CSS scope?
- You have been experimenting: Have the learning goals been stretched?

## Contexts
Dark-mode

## Restrictions
* Two-colors
* Responsive without media queries

## My concept
My idea was to create a (glitchy) terminal with a bit of storytelling. The terminal isn't quite stable and this is part of the story. This terminal is in an infinite loop that always runs into the same error and let's you do the same things over and over again. 

The concept is mostly on rails, meaning the effects mostly play automatically, but has some stages where it requires interaction from the user. I'm using different triggers to get to the next stage. 

![bbb189f535ffbdf31d260b18858d923b](https://user-images.githubusercontent.com/33430653/81548755-12df2e00-937e-11ea-9667-be4b677cbfa2.png)


### Stages
The prototype contains several stages. I took a lot of time to create workarounds with HTML and CSS to trigger the next stage.

#### Start
A start screen where the user has to press a key to start the game. I've used a textbox with autofocus and required that is hidden from the user. When the user presses a key it is actually filled in to the textbox. I can trigger a next stage/sequence with `:valid` on the textbox.

```
/* show food-service */
[trigger="start"]:valid ~ [theme] {
  display: block;
}
```

Because the textbox has required, when entering a character the textbox will become valid.

#### Theme select
Next the user will have to select a theme. The user can choose a dark-mode (default) or a classic green mode. These work with the `target` pseudoclass. This will change the theme. but also allows me to trigger the next stage.

```
#body:target [food-service], #html:target [food-service] {
  display: block;
}
```

#### Intro
Next an intro will play. No interaction from the user is required here. When the animationa are done, the menu pops up.

#### Menu
The user can select one of the four different menu's here. I've included some glitcht effects to illustrate this terminal is quite stable.


- [X] ERROR

## What I learned
- Create triggers without JS with checkboxes and input validation
- Blurring backgrounds
- Mix-blend-mode
- Create a terminal-like interface
- Better understanding of using gradients
- Transform effects
  - rotate3D
  - skew
  - transform-origin
 - ASCII art using the `pre` and `code` HTML tags
 - CSS variables
 - Seperate a smooth animation into small steps. I've used this to create a type animation.
 - Implementing automatic dark-mode
 - Implementing manual dark-mode
 - Better understanding of Flex.
 - Using `flex-grow` to take all available space.
 - Better understanding of `::after` and `::before`
 - Custom HTML attributes with CSS
 - Target pseudoclass
 - More animation properties
 - Declaring multiple animations and delays in a statement
 - Clip-path
 
 ## Sources
 - [MDN](https://developer.mozilla.org/nl/)
 - [CSS tricks](https://css-tricks.com/)
 - [Distortion effects](https://1stwebdesigner.com/trippy-css-distortion-effects/)
 - [Aperture science ASCII art](https://combineoverwiki.net/wiki/Still_Alive)
 - [Terminal styling](https://css-tricks.com/old-timey-terminal-styling/)
