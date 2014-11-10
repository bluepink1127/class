boolean up;
boolean down;
boolean left;
boolean right;
 
float x;
float y;
float speed;
 
float xSpeed = 0;
float ySpeed = 0;
 
float thrustY = 1;
float thrustX = 1;
float decay = .97;
//float maxSpeed = 15;
 
void setup(){
  size(800,800);  // Set the size of the window
  smooth();
  
  // Set ellipses and rects to CENTER mode
  ellipseMode(CENTER);
  rectMode(CENTER); 
  frameRate(30);  // 30 frames per second
  
  //initialize variables
  x=width/2;
  y=height/2;
} 
 
void move(){
   if( right ) {
        xSpeed += thrustX;
      }
      if( left ) {
        xSpeed -= thrustX;
      }
      if( up ) {
        ySpeed += thrustY;
      }
      if (down) {
        ySpeed -= thrustY;
      }
      else{
        // Deccelerate when Up Arrow key is released
        xSpeed *= decay;
        ySpeed *= decay;
      }
}
void speed(){
    y -= ySpeed;
    x += xSpeed;
}
void back(){ // when the beetle travels off-screen.
      if( y < 0 ){
        y = height;
      }
      if( y > height ){
        y = 0;
      }
      if( x < 0 ){
        x = width;
      }
      if( x > width ){
        x = 0;
      }
}
  
void drawAli(){// drawing
  background(255);  // Draw a black background 
 
  // Draw Zoog's body
  stroke(0,255,0);
  fill(#13B92D);
  rect(x,y,20,100);
  
  // Draw Zoog's head
  fill(#1AFF3E);
  ellipse(x,y-30,60,60); 
  
  // Draw Zoog's eyes
  fill(0); 
  ellipse(x-19,y-30,16,32); 
  ellipse(x+19,y-30,16,32);
  
  // Draw Zoog's legs
  stroke(0,0,255);
  strokeWeight(3);
  line(x-10,y+50,x-20,y+60);
  line(x+10,y+50,x+20,y+60);
  
}
void draw(){
  move();
  speed();
  back();
  drawAli();
     
}
 
void keyPressed() {
  if (key == CODED) {
      switch( keyCode )
      {
        case UP:
          up = true;
          break;
          
        case DOWN:
          down = true;
          break;
          
        case LEFT:
          left = true;
          break;
          
        case RIGHT:
          right = true;
          break;
      }
  }
}
 
void keyReleased() {
  if (key == CODED) {
      switch( keyCode )
      {
        case UP:
          up = false;
          break;
          
        case DOWN:
          down = false;
          break;
          
        case LEFT:
          left = false;
          break;
          
        case RIGHT:
          right = false;
          break;
      }
  }
}
