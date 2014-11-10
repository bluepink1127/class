int triangle(int base,int Height) {
return((base* Height)/2);
}

int sum(int[]intArray){
  //why sum can be reused?
  
int sum =0;
for(int i =0;i<intArray.length;i++){
    sum+=intArray[i];
  }
  return sum;
}

void setup(){
int area = triangle(4,5); // call function
//returns the int value 25
println(area);
int [] foo ={0,12,3,4,5};

println(sum(foo));
}

