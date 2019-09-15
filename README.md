# hello-world
Homework1
var bubbles = [];

function setup() {
  createCanvas(450, 600);

  for (var i = 0; i < 50; i++) {
    var bubble = {
      x: random(width),
      y: random(height),
      radius: random(10, 50)
    };
    bubbles.push(bubble);
  }
}

function draw() {
  background(255);

  for (var i = 0; i < bubbles.length; i++) {
    var bubble = bubbles[i];

    if (dist(mouseX, mouseY, bubble.x, bubble.y) < bubble.radius) {
      if (mouseIsPressed) {
        bubbles.splice(i, 5); // remove this bubble!
      }
      fill(255, 2, 268, 200);
    } else {
      fill(255, 60, 90, 200);
    }

    ellipse(bubble.x, bubble.y, bubble.radius * 2);
    bubble.x += random(-5, 5);
    bubble.y += random(-5, 5);
  }
}
