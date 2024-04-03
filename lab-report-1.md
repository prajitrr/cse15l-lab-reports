# Lab Report 1
*Prajit Rajkumar*

*PID: A17800027*

## Examples of the `cd` command:
1. With no arguments:
    1.  ```
        prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
        /Users/prajitrajkumar/lecture1
        prajitrajkumar@tuyihkj31798euoij831 lecture1 % cd
        prajitrajkumar@tuyihkj31798euoij831 ~ % pwd
        /Users/prajitrajkumar
        ```
    2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
    3. This output was produced because using `cd` without any arguments redirects the working directory to the home directory, as 
       the default directory when no arguments are provided is indeed the home directory.
    4. This output is not an error, because using `cd` without an argument simply redirects the user to the default 
       directory, the home directory, which is supposed to happen since the default directory is the home directory.

2. With a directory as an argument:
    1. ```
       prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
       /Users/prajitrajkumar/lecture1
       prajitrajkumar@tuyihkj31798euoij831 lecture1 % cd messages
       prajitrajkumar@tuyihkj31798euoij831 messages % pwd
       /Users/prajitrajkumar/lecture1/messages
       ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. This output was produced because using `cd` with a directory as an argument, given that the directory or path to the directory is present within the working directory, directs the working directory to the specified directory. This is the inherent purpose of `cd`.
   4. This output is not an error, because using `cd` with an argument that is a directory present within a working directory correctly redirects the user to the directory present, which is the purpose of the command, and this is what happened in this case. If the directory was not present, then an error would likely result.

3. With a file as an argument:
   1. ```
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd     
      /Users/prajitrajkumar/lecture1
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % cd Hello.java
      cd: not a directory: Hello.java
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
      /Users/prajitrajkumar/lecture1
      ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. This output was produced because using `cd` with a file as an argument cannot navigate to the file, given that `cd` is used for navigating to directories, and files do not themselves have a navigatable directory that can be accessed.
   4. This output is indeed an error. It is an error because the `cd` command can only navigate to directories, so attempting to navigate to a file produces an error, as a file does not have a tree of directory elements that stores other files or directories.

## Examples of the `ls` command:
1. With no arguments:
   1. ```
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
      /Users/prajitrajkumar/lecture1
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % ls
      Hello.class     Hello.java      README          messages
      ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. This output was produced because the purpose of using `ls` without any arguments is to print the contents of the current working directory. This includes files and folders, so when `ls` was used, a list of the files and folders within the `lecture1` directory was produced.
   4. The output produced is not an error.
2. With a directory as an argument:
   1. ```
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
      /Users/prajitrajkumar/lecture1
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % ls messages
      ca.txt          en-us.txt       es-mx.txt       zh-cn.txt
      ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. This output was produced because the purpose of using `ls` with an argument is to print the contents of the desired argument. `ls` with an argument prints the files and folders within a specified directory, and `messages` is a valid directory within the `lecture1` directory, so its contents are able to be listed.
   4. The output produced is not an error.
3. With a file as an argument:
   1. ```
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
      /Users/prajitrajkumar/lecture1
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % ls README
      README
      ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. This output was produced because the when using `ls` with an argument, the computer attempts to print the contents contained within the specified argument. Because the `README` file, and all other files point to only one item, themselves, the `ls` command lists out the singular file that the `README` name points to, itself.
   4. The output produced is not an error.
## Examples of the `cat` command:
1. With no arguments:
   1. ```
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
      /Users/prajitrajkumar/lecture1
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % cat
      
      ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. This output, which is no output along with the `cat` command appearing to run indefinitely was produced because the purpose of `cat` is to print out the contents of a file. If no file is specified, `cat` cannot print out the contents of any file, and it thus does not produce any output.
   4. The output produced is indeed an error because it results in the system running on the single `cat` command indefinitely and not allowing for further input, which means that the terminal needs to be killed and restarted in order to provide new inputs, a clear example of an error as this is undesired behavior.
2. With a directory as an argument:
   1. ```
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
      /Users/prajitrajkumar/lecture1
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % cat messages
      cat: messages: Is a directory
      ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. This output
   4. The output produced is indeed an error because it results in a clear error message that states `cat: messages: Is a directory`, a message that indicates that the `messages` directory does not have file contents that can be printed, since it is a directory. No output in terms of printing file content is produced, as opposed to the `cat` command's expected behavior of printing file contents.
3. With a file as an argument:
   1. ```
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd        
      /Users/prajitrajkumar/lecture1
      prajitrajkumar@tuyihkj31798euoij831 lecture1 % cat README
      To use this program:
      
      javac Hello.java
      java Hello messages/en-us.txt
      ```
   2. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   3. a
   4. The output produced is not an error.
