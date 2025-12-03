Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

Why do we use it?
It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).


Where does it come from?
Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.

The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from "de Finibus Bonorum et Malorum" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.

Where can I get some?
There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humour, or non-characteristic words etc.

5
	paragraphs
	words
	bytes
	lists
	Start with 'Lorem
ipsum dolor sit amet...'


````
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
![ alt text](https://github.com/treinartz/markdown_test/blob/main/markdown/week5-loops.gif)
