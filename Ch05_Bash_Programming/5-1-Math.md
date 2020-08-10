## 5.1 Math

### 5.1.2 Exercises

1. Look at the `man` pages for `bc`.

    ```bash
    man bc
    ```
---
2. Try doing some math in `bc` interactively.

    ```bash
    bc -l
    ```
    > When we are done, we type quit or we press ctrl + D

---
3. Try writing some equations in a file and then provide that file as an argument to `bc`.

    > We write some equations in a file
    ```bash
    echo "22 / 7" > equ.txt
    echo "3 + 4" >> equ.txt
    echo "5.2 * 6" >> equ.txt
    ```

    > We can now use one of two methods
    
    #### Method 1: Directly running bc with the file as an argument
    ```bash
    bc -l equ.txt # Will enter the interactive mode
    ```
    or
    ```bash
    bc -l < equ.txt # Won't enter the interactive mode
    ```

    #### Method 2: Pipe the file contents as arguments to the bc command
    ```bash
    cat equ.txt | bc -l # Won't enter the interactive mode
    ```
    