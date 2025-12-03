yes, except for this portfolio we are loading js filles from a js file that will look like this

*// src/data/weeks.js* export const weeks \= \[ { id: 1, title: "Canvas & Shapes", topics: "Coordinate system, basic shapes, RGB color", description: "Learning to draw on the p5.js canvas.", gifPath: "/src/assets/gifs/week1-canvas.gif", sketchUrl: "https://editor.p5js.org/your-username/sketches/xxxxx", learnings: \[ "The canvas coordinate system starts at top-left (0,0)", "Basic shapes: ellipse(), rect(), line()", "RGB color values range from 0-255" \], challenges: "Remembering that Y increases downward.", codeSnippet: \`function setup() { createCanvas(400, 400); } function draw() { background(220); fill(255, 0, 0); ellipse(200, 200, 50, 50); }\` }, *// ... more weeks* \]; \`\`\`

and a component will load the snippet  
*// src/snippets/week1.js*  
function setup() {  
  createCanvas(400, 400);  
}

function draw() {  
  background(220);  
  fill(255, 0, 0);  
  ellipse(200, 200, 50, 50);

}

Component loads the snippet:

jsx  
*// In WeekPage.jsx*  
const \[code, setCode\] \= useState('');

useEffect(() \=\> {  
  fetch(\`/src/snippets/week${weekId}.js\`)  
    .then(res \=\> res.text())  
    .then(setCode);  
}, \[weekId\]);

\`\`\`

