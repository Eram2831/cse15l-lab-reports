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

The after code works since the first code overwrites the original values before they are swapped. So in the new code, it creates an object that holds the original value so then it doesn't completely get overwrited and it gets swapped properly. Additionally, by dividing the arr.length by 2 it makes it so then the valuesa are swapped around the midpoint. If it isn't divided by 2 then the values would just go to their original positions and be wrong. 

part 2)

find command

find "____" /v /c "file path" 

a) 

```
find "WE HAVE SOME PLANES" /v /c "911report\chapter-1.txt"

---------- 911REPORT\CHAPTER-1.TXT: 730
```

In this command the /v is finding all the lines in the 911report\chapter-1.txt file that doesn't have the string: "WE HAVE SOME PLANES". Also, the /c is counting the lines given the string. So together this command is counting all the lines that don't have the phrase "WE HAVE SOME PLANES".

b) 

```
find "WE HAVE SOME PLANES" /v /c "911report\chapter-2.txt"

---------- 911REPORT\CHAPTER-2.TXT: 948
```

This time, it is counting all of the lines in the 911report\chapte-2.txt file that don't have the string: "WE HAVE SOME PLANES". Since this file doesn't contain this phrase, it just outputs number of all of the lines. 


findstr /i /n "_____" "(file path)"

a) 

```
findstr /i /n "money" "911report\chapter-2.txt"
208:                the Kingdom and other states bordering the Persian Gulf in donating money to build
627:            Bin Ladin also began to have serious money problems. International pressure on Sudan,
635:            Money problems proved costly to Bin Ladin in other ways. Jamal Ahmed al Fadl, a
644:                professed inability to provide him with money when his wife needed a caesarian
789:                state-owned Ariana Airlines to courier money into the country.
826:                tried to maintain, some autonomy. A looser circle of adherents might give money to
```

In this command it is listing all of the lines (and line number) from the file 911report\chapter-2.txt that contains the string "money". By using the findstr command I am able to output the strings that contain the string "money". The command /i and /n finds the strings that have the word "money" and outputs the full line and the line number.

b) 

```
findstr /i /n "eram" "911report\chapter-2.txt"
```

This time, since "eram" is not in any of the lines in this file, it outputs nothing.  
