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
const data = [
  { month: 'Jan', rainfall: 3.1 },
  { month: 'Feb', rainfall: 2.5 },
  { month: 'Mar', rainfall: 3.8 },
  { month: 'Apr', rainfall: 4.2 },
  { month: 'May', rainfall: 4.8 },
  { month: 'Jun', rainfall: 5.1 },
  { month: 'Jul', rainfall: 4.3 },
  { month: 'Aug', rainfall: 4.6 },
  { month: 'Sep', rainfall: 4.0 },
  { month: 'Oct', rainfall: 3.7 },
  { month: 'Nov', rainfall: 3.9 },
  { month: 'Dec', rainfall: 3.4 }
];

let springs = [];
let originY;

function setup() {
  createCanvas(800, 400);
  originY = 80;
  let spacing = width / data.length;
  data.forEach((d, i) => {
    let k = map(d.rainfall, 0, 6, 0.05, 0.2);  // spring constant
    let m = 1;                                  // mass
    let amp = map(d.rainfall, 0, 6, 20, 80);
    springs.push(new SpringMass(i*spacing + spacing/2, originY, k, m, amp));
  });
}

function draw() {
  background(240);
  springs.forEach(s => {
    s.update();
    s.display();
  });
}

class SpringMass {
  constructor(x, y0, k, m, amplitude) {
    this.pos = createVector(x, y0);
    this.y0 = y0;
    this.k = k;
    this.m = m;
    this.angle = 0;
    this.amp = amplitude;
    this.omega = sqrt(this.k / this.m);
  }
  update() {
    // simple harmonic motion: y = y0 + amp * sin(ωt)
    this.pos.y = this.y0 + this.amp * sin(this.omega * frameCount * 0.05);
  }
  display() {
    // draw spring
    stroke(0);
    line(this.pos.x, this.y0, this.pos.x, this.pos.y);
    // draw mass
    fill(200, 50, 50);
    ellipse(this.pos.x, this.pos.y, 20);
    noStroke();
    fill(0);
    textAlign(CENTER);
    text(data[springs.indexOf(this)].month, this.pos.x, this.y0 + this.amp + 30);
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
