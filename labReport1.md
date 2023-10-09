cd command:

![Image](cd screenshot.png)

Before I entered the cd command without an argument, the working directory was /home and afterwards it was still /home.
I got this output because I didn't enter a directory to change to, so it stayed the same. 
This is not an error because the directory should not have changed by using the cd command without an argument.

When I entered the cd command with the lecture1 directory as an argument, the working directory was the home directory. Afterwards the working directory was ~/lecture1 because the cd command changes the working directory, so entering lecture1 as an argument changed the working directory to that. This was not an error.

The working directory when I entered the cd command with the fr.txt as an argument was ~/lecture1/messages. The result was "bash: cd: fr.txt: Not a directory". This was an error because the the text file was not able to be the directory 


When I entered the ls command without an argument, the working directory was the home directory and the output was "lecture1". This was the output because 
