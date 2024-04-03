# Lab Report 1

## Examples of the `cd` command:
1. With no arguments:

    a.
    ```
    prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
    /Users/prajitrajkumar/lecture1
    prajitrajkumar@tuyihkj31798euoij831 lecture1 % cd
    prajitrajkumar@tuyihkj31798euoij831 ~ % pwd
    /Users/prajitrajkumar
    ```
    b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.

    c. This output was produced because using `cd` without any arguments redirects the working directory to the home directory, as 
       the default directory when no arguments are provided is indeed the home directory.
   
    d. This output is not an error, because using `cd` without an argument simply redirects the user to the default 
       directory, the home directory, which is supposed to happen since the default directory is the home directory.

2. With a directory as an argument:
    a.
    ```
    prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
    /Users/prajitrajkumar/lecture1
    prajitrajkumar@tuyihkj31798euoij831 lecture1 % cd messages
    prajitrajkumar@tuyihkj31798euoij831 messages % pwd
    /Users/prajitrajkumar/lecture1/messages
    ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   c. This output was produced because using `cd` with a directory as an argument, given that the directory 
      or path to the directory is present within the working directory, directs the working directory to the specified directory.
      This is the inherent purpose of `cd`.
   d. This output is not an error, because using `cd` with an argument that is a directory present within a working directory 
      correctly redirects the user to the directory present, which is the purpose of the command, and this is what happened in this 
      case. If the directory was not present, then an error would likely result.

3. With a file as an argument:
   a. 
   ```
   prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd     
   /Users/prajitrajkumar/lecture1
   prajitrajkumar@tuyihkj31798euoij831 lecture1 % cd Hello.java
   cd: not a directory: Hello.java
   prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
   /Users/prajitrajkumar/lecture1
   ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
   c. This output was produced because using `cd` with a file as an argument cannot navigate to the file, given that `cd` is used 
      for navigating to directories, and files do not themselves have a navigatable directory that can be accessed.
   d. This output is indeed an error. It is an error because the `cd` command can only navigate to directories, so attempting to
      navigate to a file produces an error, as a file does not have a tree of directory elements that stores other files or 
      directories.

## Examples of the `ls` command:
1. With no arguments:
   a. 
   ```
   prajitrajkumar@tuyihkj31798euoij831 lecture1 % pwd
   /Users/prajitrajkumar/lecture1
   prajitrajkumar@tuyihkj31798euoij831 lecture1 % ls
   Hello.class     Hello.java      README          messages
   ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
2. With a directory as an argument:
   a.
   ```
   ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
3. With a file as an argument:
   a.
   ```
   ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.

## Examples of the `cat` command:
1. With no arguments:
   a. 
   ```
   ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
2. With a directory as an argument:
   a.
   ```
   ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
3. With a file as an argument:
   a.
   ```
   ```
   b. The absolute path to the working directory when the command was run was `/Users/prajitrajkumar/lecture1`.
