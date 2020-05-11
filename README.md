# CSS to the Rescue @cmda-minor-web 19-20
In this course I will create an interactive webpage using CSS and HTML only. I will build features that are usually done with javascript.

I will have to pick a context and 2 restrictions as an extra challenge. I will have to think of a workaround which ultimately challenge me to be more creative!

------

## Learning goals:
- You understand the broader scope of CSS: You can show that CSS can be used for more than just styling web pages.
- You understand the progressive enhancement parts of CSS: You can show that you can use the cascade, inheritance and specificity in your project
- You understand the interactive parts of CSS: Is the UX fully enhanced within in given CSS scope?
- You have been experimenting: Have the learning goals been stretched?

------

## Contexts
Dark-mode

## Restrictions
* Two-colors
* Responsive without media queries
 
## Extra challenge
Create different triggers with CSS and HTML to trigger the next stage.

------

## My concept
My idea was to create a (glitchy) terminal with a bit of storytelling. The terminal isn't quite stable and this is part of the story. This terminal is in an infinite loop that always runs into the same error and let's you do the same things over and over again. 

The concept is mostly on rails, meaning the effects mostly play automatically, but has some stages where it requires interaction from the user. I'm using different triggers to get to the next stage. 

### Stages
The prototype contains several stages. I took a lot of time to create workarounds with HTML and CSS to trigger the next stage.

#### Start
A start screen where the user has to press a key to start the game. I've used a textbox with autofocus and required that is hidden from the user. When the user presses a key it is actually filled in to the textbox. I can trigger a next stage/sequence with `:valid` on the textbox.

![00127be0ca155a62efa4e72e3db0b0e0](https://user-images.githubusercontent.com/33430653/81550455-8b46ee80-9380-11ea-8a4d-9bddb2441be9.png)

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
![db1eb4b9075529a65061635d552bb46c](https://user-images.githubusercontent.com/33430653/81550453-8a15c180-9380-11ea-90f8-09e6a9b9daf7.png)

#### Intro
Next an intro will play. No interaction from the user is required here. When the animationa are done, the menu pops up.

![bbb189f535ffbdf31d260b18858d923b](https://user-images.githubusercontent.com/33430653/81548755-12df2e00-937e-11ea-9667-be4b677cbfa2.png)

#### Menu
The user can select one of the four different menu's here. I've included some glitchy effects to illustrate this terminal is quite stable. The menu items are dark and unreadable from the start, but become readable on hover.

![6713e13668bebc24e65c3d4eca178b23](https://user-images.githubusercontent.com/33430653/81550446-88e49480-9380-11ea-8d25-d5cd394e9add.png)

#### ERROR
The last stage happens when the user has selected a menu./ The menu fails to load and the terminal runs into a critical error. It manages to reboot its systems, but the user has to start all over again.


![9f7ff4b10a2dd8609b4e703ca1b4763b](https://user-images.githubusercontent.com/33430653/81550445-884bfe00-9380-11ea-94b6-b7532ab0944b.png)

The logo is a reference to Aperture Science from the Portal games. In this game you'll have to do all kinds of tests for a faulty AI.

### Dark mode
Dark mode is used when the user prefers dark mode in its system. All the images above are in dark-mode. I also made another theme option called Classic. This theme uses green en red as its colors.

Both dark mode and classic mode can be selected manually.

![4f563e6034057f52cf56158a02a52fdd](https://user-images.githubusercontent.com/33430653/81551630-753a2d80-9382-11ea-81cd-1fa375dbdbef.png)

### Responsive without Media queries
The concept is responsive using relative values like percentages, vh/vw and I've used flexbox.

### Two colors
I'm only using 2 colors at a time, for both dark and classic themes. Black is also used, but black is the abscence of color.

------

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
 
 ------
 
 ## Sources
 - [MDN](https://developer.mozilla.org/nl/)
 - [CSS tricks](https://css-tricks.com/)
 - [Distortion effects](https://1stwebdesigner.com/trippy-css-distortion-effects/)
 - [Aperture science ASCII art](https://combineoverwiki.net/wiki/Still_Alive)
 - [Terminal styling](https://css-tricks.com/old-timey-terminal-styling/)
