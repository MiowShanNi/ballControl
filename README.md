# ballControl
float x;
float y;
float easing = 0.05;
boolean apple = false;


void setup() {
  size(500,500); 
  noStroke();
  smooth();
  textSize(60);
  noCursor();
 
}

void draw() { 
  background(255); // background color

  
  float targetX = mouseX; // This is for easing ball
  float dx = targetX - x;
  x += dx * easing;
  
  float targetY = mouseY;
  float dy = targetY - y;
  y += dy * easing;
 
  ellipse(x, y, 66, 66); 
  
  ellipse(mouseX, mouseY, 33, 33);  // Circle at cursor
  
  fill(255,0,0,128); // Changes about the rect when the cursor reach the coordinate
  if ((mouseX <= 250) && (mouseY <= 250)) {
    rect(0, 0, 250, 250); // Upper-left
  } else if ((mouseX <= 250) && (mouseY > 250)) {
    rect(0, 250, 250, 250); // Lower-left
  } else if ((mouseX > 250) && (mouseY <= 250)) {
    rect(250, 0, 250, 250); // Upper-right
  } else {
    rect(250, 250, 250, 250); // Lower-right
  }
  
 if (mousePressed == true) {
    if (mouseButton == LEFT) {
      fill(0); // Black
    } else if (mouseButton == RIGHT) { 
      fill(126); // grey
    }
  } else {
    fill(255); // white
  }
  rect(225, 225, 50, 50);
  
  if (mousePressed && mouseX<500 && mouseY<500){

  apple=true; // boolean
    
  if (apple==true){
  
  strokeWeight(20); // stroke
  stroke (random(255),random(255),random(255)); // color of stroke

 
}}
  if (keyPressed) { 
  if (key=='S' || key == 's') // keyboard key S
  background (random(255),random(255),random(255)); // color of background
  stroke(0); // black
}
  if (keyPressed){
  if (key=='A'||key=='a') // keyboard key A
  stroke(random(255),random(255),100); // color of stroke
}

if (mousePressed == true) {
    cursor();} // for cursor

    
 fill(126); // grey
 text(key, 20, 75); // draw at coordinate (20,75)
  
  int y = 450; // create int for y
  
  fill(255); // white
  if (key == CODED) { 
    if (keyCode == UP) {
      y = 350; // coordinate of y when UP
    } else if (keyCode == DOWN) {
      y = 440; // coordinate of y when DOWN
    }
  } else {
    y = 400; 
  }
  rect(25, y, 50, 30);

}
