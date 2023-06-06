## Part 1 – Debugging Scenario
What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?

Hello I am using a MacBook Air on Visual Studio Code and I am trying to run my counting.java file. This file counts to 10 and adds the sum of the numbers as well as printing out messages while it runs. I was able to create my ```counting.java``` file by using a bash script named ```running.java``` which compiles and runs ```counting.java```. I am running this on my terminal by using javac ```counting.java``` and java counting

Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”. 

My file ```counting.java``` should count from 1 to 10 and add the sum of the numbers as well as print out messages while it runs. I am expecting to see the sum of numbers 1 through 10 which should be 55 but instead I am getting an error stating ```Exception in thread "main" java.lang.OutOfMemoryError: Requested array size exceeds VM limit at counting.main(counting.java:6)```. Currently my bashscript looks like this: 
```
#!/bin/bash

# Compile Java code
javac counting.java

# Check if compilation was successful
if [ $? -eq 0 ]; then
    echo "Java code compiled successfully."

    # Run Java program
    java counting
else
    echo "Compilation failed. Please check your Java code."
fi
```
and my java file looks like this: 
```
public class counting {
    public static void main(String[] args) {
        System.out.println("Let's count from 1 to 10 and calculate the sum!");

        int[] numbers = new int[Integer.MAX_VALUE];
        int sum = 0;
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
            sum += numbers[i];
        }
        System.out.println("\nCounting complete!");
        System.out.println("The sum of the numbers is: " + sum);
        System.out.println("Have a great day!");
    }
}
```
However my terminal is currently producing this: 
```
Let's count from 1 to 10 and calculate the sum!
Exception in thread "main" java.lang.OutOfMemoryError: Requested array size exceeds VM limit at counting.main(counting.java:6)
```
The output should say ```Let's count from 1 to 10 and calculate the sum!
1
2
3
4
5
6
7
8
9
10

Counting complete!
The sum of the numbers is: 55
Have a great day!``` 
however it is saying 
```
Let's count from 1 to 10 and calculate the sum!
Exception in thread "main" java.lang.OutOfMemoryError: Requested array size exceeds VM limit at counting.main(counting.java:6)
``` 
and I am not sure why.

When I try also running the bash command in my terminal it is saying: 
~~~
Alexiss-MacBook-Air-2:lab magdalenavega$ bash running.sh
bash: running.sh: No such file or directory
~~~

Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

I know that in order to run the terminal I need to make sure that I am in the correct directory so I did:
```
Alexiss-MacBook-Air-2:lab magdalenavega$ ls
bash            lab5.java
Alexiss-MacBook-Air-2:lab magdalenavega$ cd lab5.java
```
and then I ran the following: 
```
Alexiss-MacBook-Air-2:lab5.java magdalenavega$ javac counting.java
Alexiss-MacBook-Air-2:lab5.java magdalenavega$ java counting
```
which produced the following:
```
Let's count from 1 to 10 and calculate the sum!
Exception in thread "main" java.lang.OutOfMemoryError: Requested array size exceeds VM limit at counting.main(counting.java:6)
```
and then running the bash produced:
```
Alexiss-MacBook-Air-2:lab magdalenavega$ bash running.sh
bash: running.sh: No such file or directory
```
This is what my folders and files look like as well: 

![Image](TheFiles.png)

I looked at past assignments and feel as though I followed the same outlines and I am not sure where I am going wrong.

1. A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)
Hello I think a useful tip is to try running the command 
```
pwd
```
in your terminal. This could help you see what your directory is and if you are in the proper one where your bash script is.
I hope this could get you a better idea of where you may be going wrong. 
There also seems to be a slight error in your code and there may be an unnecessary line within your code that could be causing the error.

2. Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.

```
Alexiss-MacBook-Air-2:lab magdalenavega$ pwd
/Users/magdalenavega/Desktop/lab
```
The student was not in the proper directory which is why running bash said there was no such file and directory.

The student also took out the unnecessary line of code which made their code look like this: 
```
public class counting {
    public static void main(String[] args) {
        System.out.println("Let's count from 1 to 10 and calculate the sum!");

        
        int sum = 0;
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
            sum += i;
        }
        System.out.println("\nCounting complete!");
        System.out.println("The sum of the numbers is: " + sum);
        System.out.println("Have a great day!");
    }
}
```
and got it to produce 
```
Alexiss-MacBook-Air-2:lab5.java magdalenavega$ java counting
Let's count from 1 to 10 and calculate the sum!
1
2
3
4
5
6
7
8
9
10

Counting complete!
The sum of the numbers is: 55
Have a great day!
```
3. At the end, all the information needed about the setup including:
-The file & directory structure needed
![Image](TheFiles.png)

-The contents of each file before fixing the bug
```
counting.java
```
```
public class counting {
    public static void main(String[] args) {
        System.out.println("Let's count from 1 to 10 and calculate the sum!");

        int[] numbers = new int[Integer.MAX_VALUE];
        int sum = 0;
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
            sum += numbers[i];
        }
        System.out.println("\nCounting complete!");
        System.out.println("The sum of the numbers is: " + sum);
        System.out.println("Have a great day!");
    }
}
```
```
running.sh
```
```
#!/bin/bash

# Compile Java code
javac counting.java

# Check if compilation was successful
if [ $? -eq 0 ]; then
    echo "Java code compiled successfully."

    # Run Java program
    java counting
else
    echo "Compilation failed. Please check your Java code."
fi

```
-The full command line (or lines) you ran to trigger the bug
```
bash  running.sh
```

-A description of what to edit to fix the bug

The bug was both within the code and also within the strcuture of the files. To fix the code the student had to remove what was in line 4 as well as fix what was in line 10. The first line was unnecessary and all that was needed was to make the sum increase based off of i when it passes in the for loop. This fixed the code and got it to run when simply using ```javac counting.java``` and ```java counting``` but it did not fix the bash problem. To fix the bash problem using the command pwd was necessary to check if you are in the correct directory in order to make the bash call. The student first had to ```ls``` to see their directory and then ```cd bash``` in order to get into the folder where ```running.java``` was located. Being in the correct directory was what ended up making ```bash running.sh``` to work producing the following:

```
Let's count from 1 to 10 and calculate the sum!
1
2
3
4
5
6
7
8
9
10

Counting complete!
The sum of the numbers is: 55
Have a great day!
```

## Part 2 – Reflection
During the second half of the quarter, I learned about vim and its various commands and features. Vim is a text editor that has a wide range of functionalities and modes such as normal, insert and visual. Within these modes there are many cool features and navigation techniques through the use of your keys on your keyboard. 
~~~
h
~~~
moves your cursor to the left one line
~~~
l
~~~
moves your cursor to the right one line 
~~~
j
~~~
moves your cursor down one line
~~~
k
~~~
moves your cursor up one line
~~~
x
~~~
deletes what your cursor is on
~~~
:wq
~~~
saves your edits and quits
Those are some of the many features I was able to learn through vim and it was one of the most interesting subjects we discussed. Walking through the tutorial on our terminal was really fun and was what made me learn it the best, making it my favorite topic discussed second half of the quarter.

