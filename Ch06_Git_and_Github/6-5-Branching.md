## 6.5 Branching

### 6.5.2 Exercises

1. Start a new branch.

    ```bash
    $ git branch new_branch
    ```

2. Switch to that branch and add commits to it. Switch to an older branch and then merge the new branch into your current branch.

    ```bash
    $ git checkout new_branch

    $ echo "some text" >> file.txt

    $ git add -A # or git add file.txt

    $ git commit -m "changed file.txt"

    $ git checkout master
    
    $ git merge new_branch
    ```

3. Purposefully create and resolve a merge conflict.

    ```bash
    $ git checkout new_branch
    
    $ echo "hello Marvel" >> file.txt
    
    $ git add -A
    
    $ git commit -m "saying hello Marvel"

    $ git checkout master
    
    $ echo "hello DC" >> file.txt
    
    $ git add -A
    
    $ git commit -m "saying hello DC"
    
    $ git merge new_branch # A conflict will be prompted
    ```
    > We then open the file where confilct happened and resolve it.
    
    > Choose which change we will adopt, then save and exit.

    ```bash
    $ git add -A
    $ git commit -m "resolved conflict"
    ```
    > C'mon, we all know who won the conflict :P
    
    > It's your preferred universe :) (Mine is Marvel BTW)
