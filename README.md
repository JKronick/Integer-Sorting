# Integer-Sorting
Sorts integers up to 20 times faster than merge sort. I have heard radix sort does the same thing so I would like to compare my algarithm with radix.
public static int [] sort(int [] array){
    int large = array[0];
    int min = array[0];
    for(int i=1; i<array.length; i++){
      if(array[i] > large){
        large = array[i];
      }else if(array[i]<min){
        min = array[i];
      }
    }
    int [] sArray = new int[large-min+1];
    for(int d=0; d<array.length; d++){
      sArray[array[d]-min]++;
    }
    large=0;
    for(int u=0; u<sArray.length; u++){
      for(int c=0; c<sArray[u]; c++){
        array[large] = min+u;
        large++;
      }
    }
    
    return array;
  }
