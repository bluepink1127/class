/**
Simple ball bouncing animation.  try changing the values of xSpeed and ySpeed to modify the animation.
Changing the initial x and y values as well as the size() will also modify the behavior of the ball.
This is a simple animation, but it covers a lot of fundamental aspects of programmatic animation.
*/
//location of ball
int x = 10;
int y = 20;
//how much the ball moves on each frame
int xSpeed = 5;
int ySpeed = 5;
 
void setup() {
  size(400, 300);
}

void moveBall(){
  x = x + xSpeed; //move along x axis
  y = y + ySpeed; //move along y axis
}  
void checkBoundary(){
  if (x > width || x < 0) { // are we out of bounds?
    xSpeed = xSpeed *-1; //reverse direction of x
  } 
  if (y > height || y < 0) {// are we out of bounds?
    ySpeed = ySpeed *-1; //reverse direction of y
  }
}
 
void draw() {
  background(100, 0, 0); //dark red
  //step 1 -moveball
  moveBall();
 //step 2 -checkBoundary
  checkBoundary();
  //step3-draw circle
  ellipse(x, y, 10, 10); //draw the ball
}
