```css

// Tips: 
// 1. How to change the origin of where things should pin
transform-origin: 10px 10px;

// 2. Set logo as background-image, set the text-indent to -10000;

// 3. Use color black with different opacity to create illusion of color scheme. 

// 4. Font smoothing 
body {
    -webkit-font-smoothing: antialiased;
}

/* 
TheNetNinja: CSS Animation
- transform
    - translate
    - scale
    - rotate 
- transition
    - property, time, delay, timing function
- keyframes
*/

// 1. You set the ending state in the :hover or in a different class, then you add the transition property in the initial state, the computer will handle the rest. 

// Example: 

.button {
    color: red;
    font-size: 15px;
    transition: all 1s ease-in-out;
}

.button:hover {
    color: green;
    transform: scale(1.05) translate(-20px, 0px);
}

// When the mouse is hovering over the button, the animation will happen.

// 2. Another powerful idea in CSS animation is keyframes. You set a name for the animation and decide what it will be in any point in time. 

@keyframes drive {
    from {

    }

    to {

    }
}

.car {
    animation-name: drive;
}

@keyframes jump {
    0% { }
    10% { }
    100% { }
}

.human {
    animation-name: jump;
    animation-duration: 3s;
    animation-fill-mode: (forwards, backwards, both);
    animation-delay: 2s;
    animation-iteration-count: (3, infinite);
    animation-direction: reverse (alternate, alternate-reverse, normal);
    animation-timing-function: ease;
    animation-play-state: ;
    animation: name duration delay timing function iteration-count direction;
}

// The fundamentals of CSS Animation ends here. 

// Code for animation using jQuery (click)

$('button').on('click', function() {
    $(this).closest('li')
    .find('img')
    .clone()
    .addClass('zoom')
    .appendTo('body');

    setTimeout(function() {
        $('zoom').remove();
    }, 1000);
})

/*
TheNetNinja - CSS Flexbox 
Flexbox is good for one direction, you set it by display: flex on the parent element.
*/

flex-grow: can be used as grid system. 
flex-shrink: the rate they shrink
flex-wrap: will wrap the element if it hits the min-width / flex-basis property
flex-basis: is like min-width but it will shrink when the browser is too small

flex: flex-grow flex-shrink flex-basis;

/* 
TheNetNinja: CSS Grid 
Css Grid is a 2 dimension positioning system. It's not hard to learn, just a few fundamentals concepts
*/

// 1. First, we need to set the parent container to a display of grid

display: grid;

// 2. Then we need to specify how many columns (important) and rows (optional) that the grid have

grid-template-columns: repeat(12, 1fr); //repeat 12 times with each col contain 1 fraction
grid-template-rows: ;

// minmax will set the height of the row
grid-auto-rows: minmax(100px, auto);

grid-gap: 10px;

// 3. We can control it freely by using grid-area and grid-template-area. 

// Example code: 

.container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: minmax(100px, auto);
    grid-gap: 10px;
    grid-template-areas: 
    "header header header header"
    "section section . ."
    "footer footer footer footer";   
}

// The dot is empty space in the grid

header {
    grid-area: header;
}

footer {
    grid-area: footer;
}

section {
    grid-area: section;
}

















```