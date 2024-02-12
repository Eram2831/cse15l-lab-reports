part 1)

a.

```  
int[] input2 = {1,2,3};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{3,2,1}, input2);
```

b. 

```  
int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
```

c. 

![Image](symptom.png)

d.

before code:

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

after code:

```
static void reverseInPlace(int[] arr) {
    for (int i = 0; i < arr.length / 2; i++) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```

e. 

The after code works since the first code overwrites the original values before they are swapped. So in the new code, it creates an object that holds the original value so then it doesn't completely get overwrited and it gets swapped properly. Additionally, by dividing the arr.length by 2 it makes it so then the valuesa are swapped around the midpoint. Additionally, if it isn't divided by 2 then the values would just go to their original positions and be wrong. 
