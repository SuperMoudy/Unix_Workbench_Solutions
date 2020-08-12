## 6.3 Getting Started with Git

### 6.3.2 Exercises

1. Start a repository in a new directory.

    ```bash
    $ mkdir new_directory

    $ cd new_directory

    $ git init
    ```

2. Create a new file in your new Git repository. Make sure Git is tracking the file and then create a new commit.

    ```bash
    $ touch new_file.txt

    $ echo "This is a new file" > new_file.txt

    $ git add new_file.txt

    $ git commit -m "Added a new file"
    ```

3. Make changes to the file, and then commit these changes.

    ```bash
    $ echo "This is the second line in the new file" >> new_file.txt

    $ git add new_file.txt

    $ git commit -m "Edited the new file"
    ```

4. Add two new files to your repository, but only commit one of them. What is the status of your repository after the commit?

    ```bash
    $ touch file1.txt file2.txt

    $ git add file1.txt

    $ git commit -m "Added another one file"

    $ git status # Output:
    ```

    ```
    Untracked files:
      (use "git add <file>..." to include in what will be committed)

	    file2.txt    
    ```

5. Undo the last commit, add the untracked file, and redo the commit.

    ```bash
    $ git reset --soft HEAD~ # or HEAD~1
    
    $ git add -A
    
    $ git commit -m "Added another two files"
    ```
