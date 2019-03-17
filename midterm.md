# hw7
var s = 4;
var k = 2;
var x = 500;
var y = 200;
var value1 = 20;
var value2 = 20;
var value3 = 120;
var song, analyzer;

function preload() {
  song = loadSound('ball.wav');
}

function setup() {
  createCanvas(600, 500);
  colorMode(HSB, 360, 100, 100, 100);
  background(359, 0, 99);

}

function draw() {
  fill(0, 10);
  noStroke();
  rect(0, 0, width, height); 
  fill(value1, value2, value3);



  x += s;
  y += k;

  ellipse(x, y, mouseX / 3, mouseX / 3);
  if (x > width - 25 || x < 25) { 
   s += random(-2, 2);
    if (s >= 100) {
      s = 1;
    }
    s *= -1;
    song.play();
  }
  if (y > height - 25 || y < 25) { 
    k += random(-1, 1);
    k *= -1;
    song.play();
  }

}

function mousePressed() {

  value1 = random(40, 180);
  value2 = random(60, 100);
  value3 = 255;

}
