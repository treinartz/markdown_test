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
var x;       // center x-position of the face
var y;       // center y-position of the face
var diam;    // size of the main face circle

function setup() {
  createCanvas(400, 400);
  angleMode(DEGREES);  // Use degrees for arc angles (easier to read)

  x = width / 2;       // Place face in the middle horizontally
  y = height / 2;      // Place face in the middle vertically
  diam = 100;          // Face diameter
}

function draw() {
  background(220);
  // ---- Main face circle ----
  fill(255, 255, 0);   // Yellow face color
  stroke(0);           // Black outline
  strokeWeight(2);
  ellipseMode(CENTER);
  ellipse(x, y, diam, diam);

  // ---- Smile ----
  var startAng = 0.1 * 180;   // Start of smile arc
  var endAng   = 0.9 * 180;   // End of smile arc
  var smileDiam = 0.6 * diam; // Smile size based on face size

  noFill();
  arc(x, y, smileDiam, smileDiam, startAng, endAng);

  // ---- Eyes ----
  var offset = 0.2 * diam;    // Distance from center to eyes
  var eyeDiam = 0.1 * diam;   // Eye size based on face

  fill(0);
  ellipse(x - offset, y - offset, eyeDiam, eyeDiam); // Left eye
  ellipse(x + offset, y - offset, eyeDiam, eyeDiam); // Right eye
}
// Save the drawing when “d” is pressed
function keyPressed() {
  if (key == "d") {
    save("myArtwork.png");
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
