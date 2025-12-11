# Here is week 0 in markdown 
[see the markdown cheatsheet:](https://www.markdownguide.org/cheat-sheet/)

You will need these 6 items in each weeks's digital notebook markdown file from week 1- week 10: (see the items listed next to their numbers below)

1. Detailed description for what the code does
2. Thorough and thoughtful reflection on the process including challenges and solutions
3. an image or animated gif of the program (see the code below)
4. The commented code that made the program 
5. A link to the p5 editor with the program
6. References for code produced elsewhere

```javascript
// Save PNG when a key is pressed
function keyPressed() {
  if (key == "d") {
    save("myArtwork.png"); // Saves as a PNG file
  }
}
// Save gif for animated programs when a key is pressed
function keyPressed() {
  if (key == "s") {
    saveGif("myAnimation", 5); // "myAnimation.gif", 5-second duration
  }
}
```

---
## Github markdown "Digital Course Notebook" for Weekly Graphics Assignments

- Remember your weekly graphics program does not have to look like anyone else's, 
so,  think out of the box and make it unique by exploring the topic through a program you choose.  
- Coding provides many opportunities to make and learn from mistakes.
so, learn to embrace your mistakes as an essential and welcome part of the process.

## 1. Description:  What does the code do?
In a paragraph, describe/explain what your program does, and how it works.   What understanding can you carry forward to the next challenge? 


## 2. Reflection:  What were challenges and solutions?
In a paragraph, 
- Explain/describe at least two significant programming challenges you faced this week and/or with this assignment.  Then describe how you solved them including references for or credit given to outside sources and/or assistance.
- Explain/describe what additional functionality you might consider...think of at least two ideas that could extend what you created.
- Explain/describe what you might do differently if you were to start over from scratch...and be specific!  Consider writing  it for a student about to embark on the same journey…
- Evaluate your independent problem solving process and progress this week in a paragraph.
- For written reflections, it may be easier to write using Google docs or similar word processor.  Then, copy and paste your written responses into your markdown file.

## Assignment/end of week checklist
- did you submit on time
- did you reflect, describe, and post your gif
- did you comment on another students work with suggestions for next steps
- did you practice **PRIM(M) (Predict, Run, Investigate, Modify)** before Making your own?
- did you participate fully this week

## Rubric
- reflection, writing, and evaluation in Github notebook is thorough, thoughtful, and detailed with examples to illustrate ideas 
- relfection/writing clearly indicates efforts that were independent, collaborative, and/or assisted through attribution of sources
- reflection/writing clearly indicates evidence of practice and aspirations for growing independent problem solving
- submitted on time 

here are the 3 items I learned
1. First item
2. Second item
3. Third item

---

## 4. The code that you wrote about above.
````javascript
var x;        // Will store the x-coordinate of the face center
var y;        // Will store the y-coordinate of the face center
var diam;     // Will store the diameter of the main face circle

function setup() {
  createCanvas(400, 400); 
  // Creates a 400×400 drawing area.
  // p5.js automatically calls draw() 60 times per second.

  angleMode(DEGREES);
  // arc() expects angles. By default p5 uses radians.
  // Switching to degrees makes 0–360 intuitive for beginners.

  x = width / 2;
  y = height / 2;
  // Center the face by using the canvas midpoint.
  // This makes the drawing scalable and easier to modify.
  
  diam = 100;
  // Using one variable for the face size allows all features
  // (eyes, smile, etc.) to scale proportionally.
}

function draw() {
  background(220);
  // Refresh the screen each frame.
  // Light gray creates a neutral background that highlights the face.

  // -------------------------------------------------------------
  // DRAW THE MAIN FACE CIRCLE
  // -------------------------------------------------------------
  fill(255, 255, 0); 
  // Solid yellow makes the emoji recognizable.

  stroke(0); 
  // Black outline makes the face visually crisp.

  strokeWeight(2);
  // Slightly thicker outlines give a cartoon-like style.

  ellipseMode(CENTER);
  // Makes the ellipse use its center point (more intuitive for faces).

  ellipse(x, y, diam, diam);
  // Draws the main face.
  // Because we control x, y, and diam independently,
  // scaling and repositioning the emoji becomes trivial.

  // -------------------------------------------------------------
  // DRAW THE SMILE 
  // -------------------------------------------------------------
  // The smile is drawn using an arc. We use percentages of the face size
  // so enlarging the face keeps the proportions consistent.

  var startAng = 0.1 * 180;
  var endAng   = 0.9 * 180;
  // The smile arc goes from 18° to 162°.
  // These percentages create a wide, friendly smile.
  // Multiplying by 180 corresponds to the semicircle direction.

  var smileDiam = 0.6 * diam;
  // The smile should be smaller than the face.
  // 0.6 keeps it centered and visually pleasing.

  noFill();
  // A smile is just a curved line, so we remove interior fill.

  arc(x, y, smileDiam, smileDiam, startAng, endAng);
  // Because ellipseMode is CENTER, this arc stays centered on the face.
  // Using equal width and height creates a perfect circular arc.

  // -------------------------------------------------------------
  // DRAW THE EYES
  // -------------------------------------------------------------
  // Again, we use proportional measurements so everything scales cleanly.

  var offset = 0.2 * diam;
  // Moves the eyes 20% of the face diameter away from the center.
  // This controls both horizontal and vertical spacing.

  var eyeDiam = 0.1 * diam;
  // Keeps eye size proportional to overall face size.

  fill(0);
  // Eyes are black, which is standard emoji style.

  ellipse(x - offset, y - offset, eyeDiam, eyeDiam);
  // Left eye:
  //  - Shift left by offset
  //  - Shift upward by offset (eyes sit above midline)

  ellipse(x + offset, y - offset, eyeDiam, eyeDiam);
  // Right eye, mirrored across the center.

  // Using offsets makes the face adaptable:
  // Change diam → whole face resizes automatically.
}
// -------------------------------------------------------------
// SAVE ARTWORK WHEN "d" KEY IS PRESSED
// -------------------------------------------------------------
function keyPressed() {
  if (key == "d") {
    save("myArtwork.png");
    // p5.js captures the current canvas and downloads it.
    // This is great for a classroom "save your art" moment.
  }
}


````
## 3. The gif created from the code above.
![image info](https://github.com/treinartz/markdown_test/blob/main/week0/week5-loops.gif)
## 5. Link to the code
[link to the code:](https://www.cnn.com/)
## 6. The references/attrubutons used for assistance
- source: Who/what assisted with the program?
- date: When was this code retrieved or assistance rendered
