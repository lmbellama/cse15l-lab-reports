
Part 1 - Debugging Scenario

1)Student's post:

The symptom below was a result of trying to run a bash file with the argument "hello". The bash file is supposed to compile and run another file, palindromeChecker.java, with the command line argument as the argument. Maybe the bug is a complication with compiling the file that the bash file is supposed to run.

![image](https://github.com/lmbellama/cse15l-lab-reports/assets/130100171/8095c00f-d6be-4fde-9be0-e8252e8ac6c5)


2)TA's Response:

Well you could try compiling and running your palindromeChecker.java file from the command line to see if it will cause an error. If there is no error, then the bug could be a problem with calling the file in your bash file.

3)Student's Response:


![image](https://github.com/lmbellama/cse15l-lab-reports/assets/130100171/dc66caf0-a582-4e9e-9658-34d15f8210d3)


What I learned from entering the command `javac *.java`, was that the .java files in the current directory can be compiled without an issue. The bug isn't in the palindromeChecker.file because I was able to call it the the argument "hello" and got the correct output. And I learned that the bug is in the line of code in the bash file that calls palindromeChecker.java, which is the line `java -cp palindromeChecker $@` because when I entered that line in the terminal with and without an argument, there were errors. When I entered that line with the same argument as before, "hello", it produced the same error message as before. The terminal output when I tried the line without an argument was a list of the ways `java` command can be used as well as the options compatable with it. This tells me that that line in the bash script incorrectly uses the `java` command.

The bug that was causing the errors was the `-cp` option that I had in the third line of the test.sh file where I called the palindromChecker class after compling all the .java files in the directory. This was causing issues because using the `-cp` option with the `java` command without entering a classpath causes an error. 

4)Setup Information:

-file and directory structure:

![image](https://github.com/lmbellama/cse15l-lab-reports/assets/130100171/0f8ccab9-ce6a-48c6-ae50-e6ed376178e6)

The only files I needed were the files palindromeChecker.java and test.sh, which were both in my labReport5 directory.

-contents of files before fixing the bug 

test.sh:

![image](https://github.com/lmbellama/cse15l-lab-reports/assets/130100171/6a91d8e8-e1c5-4d5d-ba83-64dfafaa4b46)

palindromeChecker.java:

![image](https://github.com/lmbellama/cse15l-lab-reports/assets/130100171/f1247456-5c7b-4bd9-bb98-e193ec6b9d2e)

-contents of files after fixing the bug

test.sh:

![image](https://github.com/lmbellama/cse15l-lab-reports/assets/130100171/5fb7f769-5fad-4d39-83b7-b03fcc4bfedb)


palindromeChecker.java:

![image](https://github.com/lmbellama/cse15l-lab-reports/assets/130100171/f1247456-5c7b-4bd9-bb98-e193ec6b9d2e)

-command line/s that triggered the bug

![Image](terminalError.PNG)

The failure-inducing inputs that caused this symptom were the terminal commands `bash test.sh hello` and `bash tesh.sh`  

-description of edits

The edit that was made to fix the bug was deleting the `-cp` from the third line of the test.sh file. 
