## Chapter 3: Command Line Basics

### 3.1.2 Exercises

1. Print your name to the terminal.

    ```bash
    $ echo SuperMoudy
    ```

2. Clear your terminal after completing #1.

    ```bash
    $ clear
    ```
---

### 3.2.2 Exercises

1. Set your working directory to the root directory.

    ```bash
    $ cd /
    ```

2. Set your working directory to your home directory using three different commands.

    - Method 1:
    ```bash
    $ cd
    ```

    - Method 2:
    ```bash
    $ cd ~
    ```
    - Method 3: Absolute Path
    ```bash
    $ cd /path/to/your/home/directory
    ```

3. Find a folder on your computer using your file and folder browser, and then set your working directory to that folder using the terminal.

    ```bash
    $ cd path/to/the/folder
    ```

4. List all of the files and folders in the directory you navigated to in #3.

    ```bash
    $ ls folder
    ```
---

### 3.3.2 Exercises

1. Create a new directory called workbench in your home directory.

    ```bash
    $ cd

    $ mkdir workbench
    ```

2. Without changing directories create a file called readme.txt inside of workbench.

    ```bash
    $ touch workbench/readme.txt
    ```

3. Append the numbers 1, 2, and 3 to readme.txt so that each number appears on it’s own line.

    ```bash
    $ echo 1 > workbench/readme.txt

    $ echo 2 >> workbench/readme.txt
    
    $ echo 3 >> workbench/readme.txt
    ```

4. Print readme.txt to the command line.

    ```bash
    $ cat workbench/readme.txt
    ```

5. Use output redirection to create a new file in the workbench directory called list.txt which lists the files and folders in your home directory.

    ```bash
    $ ls > workbench/list.txt
    ```

6. Find out how many characters are in list.txt without opening the file or printing it to the command line.

    ```bash
    $ wc -c workbench/list.txt
    ```
---

### 3.4.2 Exercises

1. Create a file called message.txt in your home directory and move it into another directory.

    ```bash
    $ cd
    
    $ touch message.txt
    
    $ mv message.txt path/to/another/directory
    ```

2. Copy the message.txt you just moved into your home directory.

    ```bash
    $ cd
    
    $ cp path/to/another/directory/message.txt message.txt
    ```

3. Delete both copies of message.txt. Try to do this without using rm.

    > We firstly want to find an alternative to rm:

    ```bash
    $ apropos remove
    ```

    > Found a command called unlink
    
    ```bash
    $ unlink message.txt path/to/another/directory/message.txt
    ```
