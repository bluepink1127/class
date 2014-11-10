void setup(){
  background(0);
  size(500,500);
}
void RECT(int x,int y,int diameter){
  rectMode(CENTER);
  rect(x,y,diameter,diameter) ;
  fill(255);
  
}
void draw(){
  for(int i=0;i<100;i++){
    int sx = int (random(width));
    int sy = int (random(height));
    int size = int( random(5,100));
  RECT(sx,sy,size);
  }
}
