
String numbers = "8 67 5 309";
int[] nums = int(split(numbers, ' '));
String []numsArray = new String[nums.length];


for (int i = 0; i < nums.length; i++ ) { 
    nums[i]+=30;
    numsArray[i] = nf(nums[i],0);
    
}

String newNumbers = join(numsArray,"  ");
println(newNumbers);
