part 1)

a. A failure-inducing input for the buggy program, as a JUnit test and any associated code

```  
int[] input2 = {1,2,3};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{3,2,1}, input2);
```

b. An input that doesn't induce a failure, as a JUnit test and any associated code

```  
int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
```

c. The symptom, as the output of running the tests

![Image](symptom.png)

d. The bug, as the before-and-after code change required to fix it 

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

find . -size 
 
a) 
working directory: home

```
find . -size +1M

./docsearch/.git/objects/pack/pack-3c507e52543aff4f852f6a72e1db9cdd79a486b8.pack
```

In this command it ifnds all files that islarger than 1 megabyte. This is useful because it shows files that are too big or too small. 

b) 
working directory: ./technical

```
find ./docsearch -type d -size -2G
./docsearch
./docsearch/.git
./docsearch/.git/branches
./docsearch/.git/logs
./docsearch/.git/logs/refs
./docsearch/.git/logs/refs/heads
./docsearch/.git/logs/refs/remotes
./docsearch/.git/logs/refs/remotes/origin
./docsearch/.git/objects
./docsearch/.git/objects/pack
./docsearch/.git/objects/info
./docsearch/.git/info
./docsearch/.git/hooks
./docsearch/.git/refs
./docsearch/.git/refs/heads
./docsearch/.git/refs/remotes
./docsearch/.git/refs/remotes/origin
./docsearch/.git/refs/tags
./docsearch/lib
./docsearch/technical
```

This time, showing all the directories that are less than 2 gigabytes. This is useful to find files that are too big or small. 


find -mmin 

a) 
working directory: ./docsearch/technical/911report

```
find . -mmin -3
./chapter-1.txt
```

In this command it is outputting the file that was last modified in the last 3 min, I modified chapter-1.txt file a few minutes ago so it outputs chapter-1.txt. This is useful because it helps us identify files that were recently modified rather than looking through each file to locate the last file we modified. 

b) 
working directory: ./docsearch/technical

```
find ./docsearch/technical -type d -mmin +1
./docsearch/technical/911report
./docsearch/technical/biomed
```

This time, it is showing all the directories that were modified more than 1 minute ago. Since the 911report and biomed directories were recently modified, they are the output. 

find -exec
working directory: home

a)

```
find . -name "*chapter*" -exec rm '{}' ';'
```

In this command there is no output, instead it uses the -exec command and rm to delete all files that have "chapter" in it. This is useful so then you don't have to delete each file manually and instead altogether. 

b) 

```
find ./docsearch/technical/biomed -type d -exec rm -r {} +
```

This time I am doing it with a directory, I am deleting a whole directory using the -exec command and the rm. This is useful to get rid of a whole directory rather than locating it and deleting it manually. 

find -iname

a) 

```
find -name "Chapter-1.txt"
find -iname "Chapter-1.txt"
./docsearch/technical/911report/chapter-1.txt
```

This time, I am showing the output of find -name "Chapter-1.txt" which has no output since there are no files that are named Chapter-1.txt. However when u do find -iname "Chapter-1.txt" it outputs ./docsearch/technical/911report/chapter-1.txt since it is now case insensitive. This is useful because sometimes we could accidentally put a letter in capital on accident. 

b)

```
find -name "911Report"
find -iname -type d "911Report"
./docsearch/technical/911report
```

This time, I am doing the same thing but for directories. When doing -name "911Report" it doesn't show any output. However when doing -iname "911Report" it shows the directory with the name 911report no matter if it has a capital R or a lower case r. 
