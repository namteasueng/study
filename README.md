# study

##Eye Class

let e1, e2, e3;

function setup() {
  createCanvas(640, 360);
  noStroke();
  e1 = new Eye(250, 16, 120);
  e2 = new Eye(164, 185, 80);  
  e3 = new Eye(420, 230, 220);
}

function draw() {
  background(102);
  
  e1.update(mouseX, mouseY);
  e2.update(mouseX, mouseY);
  e3.update(mouseX, mouseY);

  e1.display();
  e2.display();
  e3.display();
}

class Eye {
  constructor(tx, ty, ts) {
    this.x = tx;
    this.y = ty;
    this.size = ts;
    this.angle = 0.0;
  }

  update(mx, my) {
    this.angle = atan2(my-this.y, mx-this.x);
  }
  
  display() {
    push();
    translate(this.x, this.y);
    fill(255);
    ellipse(0, 0, this.size, this.size);
    rotate(this.angle);
    fill(153, 204, 0);
    ellipse(this.size/4, 0, this.size/2, this.size/2);
    pop();
  }
}
***
let img;

function preload(){
   img = loadImage("https://ichef.bbci.co.uk/news/976/cpsprodpb/4FB7/production/_116970402_a20-20sahas20barve20-20parrotbill_chavan.jpg");
}
function setup() {
  createCanvas(400, 400,WEBGL);
  //image(img,0,0,img.width/2, img.height/2);
}

function draw(){
  background(120);
  rotateX(mouseX/20);
  rotateY(mouseY/20);
  //lotatez(45);
  texture(img);
  sphere(100);
  //box(100);
}
