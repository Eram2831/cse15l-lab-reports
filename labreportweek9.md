a) Debugging Scenario


student: 

![image](https://github.com/Eram2831/cse15l-lab-reports/assets/156246166/7bc5accf-4af0-4340-9b5d-6e0b0b0305f9)


Hi I am not completely sure what is wrong with the code, it says that there is a problem on line 20 and 21 in the TestListExamples file. I believe there is something wrong with the StringChecker but I'm not completely sure what is the problem. 


TA: 

Hi student! Take a look at this link: https://ucsd-cse11-f21.github.io/lectures/lecture10.html

It should help you figure out what the problem is. 


student: 

![image](https://github.com/Eram2831/cse15l-lab-reports/assets/156246166/6f56fde3-45a5-444a-8888-a1eebf65fc1f)



![image](https://github.com/Eram2831/cse15l-lab-reports/assets/156246166/c66a5e83-b829-42bd-8631-20df8c5c096d)



![image](https://github.com/Eram2831/cse15l-lab-reports/assets/156246166/939e765b-8d42-4b55-9848-60ffc612f8c1)


It worked! I checked out the link that you sent about interfaces and found that I was trying to make an object of the StringChecker class even though it is a interface and not a class. So I created a `IsMoon()` class and created an object using that class. 


All information needed about the setup: 

Directory Structure: ![image](https://github.com/Eram2831/cse15l-lab-reports/assets/156246166/eb49fd86-513b-4e97-8ba5-7c4d39cd150c)


The contents of each file before fixing the bug:
![image](https://github.com/Eram2831/cse15l-lab-reports/assets/156246166/ff2ce4b2-6f92-4308-940f-b558d8b17e97)

$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected

To fix the bug, you have to create a class that implements the StringChecker interface. Then you would have to go to lines 20 and 21 and switch the `new StringChecker()` on both lines to the name of the class, in this case `IsMoon()`. 
