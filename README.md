# java
https://editor.p5js.org/NAT22/sketches/-XilF-Hr5
<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.8.0/p5.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.8.0/addons/p5.sound.min.js"></script>
    <link rel="stylesheet" type="text/css" href="style.css">
    <meta charset="utf-8" />

  </head>
  <body>
    <main>
    </main>
    <script src="sketch.js"></script>
  </body>
</html>

let cor;
let circuloX; // horizontal
let circuloY; // vertical

function setup() {
  createCanvas(900, 900);
  background(color(0, 100));
  cor = color(random(0, 100), random(0, 255), random(0, 255));

  circuloX = [0, 0, 0, 0, 0, 0];
  circuloY = [random(height), random(height), random(height), random(height),  random(height), random(height)];

  
}

function draw() {
  
  fill(cor);

  for(let contador in circuloX) {
    rect(circuloX[contador], circuloY[contador], 50);    
    circuloX[contador]+= random(0,3);
    circuloY[contador]+= random(-3,3); 
    
    if(circuloX[contador] >= width){
      circuloX[contador] = 0;
      circuloY[contador] = random(height);
    }
  }
  for(let contador in circuloX) {
    circle(circuloX[contador], circuloY[contador], 50);    
    circuloX[contador]+= random(0,3);
    circuloY[contador]+= random(-3,3); 
    
    if(circuloX[contador] >= width){
      circuloX[contador] = 0;
      circuloY[contador] = random(height);
    }
  }
  
  if(mouseIsPressed){
    cor = color(random(0, 255), random(0, 255), random(0, 255), random(0, 100));
  }
}

html, body {
  margin: 0;
  padding: 0;
}
canvas {
  display: block;
}
