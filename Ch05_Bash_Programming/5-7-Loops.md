## 5.7 Loops

### 5.7.5 Exercises

- Write several programs with three levels of nesting and include FOR loops, WHILE loops, and IF statements. Before you run your program try to predict what your program is going to print. If the result is different from your prediction try to figure out why.

    ```bash
    #!usr/bin/env bash
    # File: ex5-7-q1.sh

    # Possible cases:
    # Case 1: while ---> for ---> if
    # Case 2: if ---> While ---> for
    # Case 3: for ---> if ---> while
    # Case 4: if ---> for ---> while
    # Case 5: for ---> while ---> if
    # Case 6: while ---> if ---> for

    # But I will choose only case 5 
    # (Try other cases by yourself)
    # Goal of my example:
    # Printing multiples of array elements that are
    # greater than 20 and less than 80
    for i in ${arr[*]}
    do
        let j=0
        echo "For number $i:"

        while [[ $j -lt 10 ]]
        do
            let n=$i\*$j

            if [[ $n -gt 20 ]] && [[ $n -lt 80 ]]
            then
                echo $n
            fi

            let j=$j+1
        done

        echo ""
    done
    ```

- Enter the `yes` command into the console, then stop the program from running. Take a look at the `man` page for `yes` to learn more about the program.

    ```bash
    #!usr/bin/env bash
    # File: ex5-7-q2.sh

    yes "level up" # Inspired by Ciara :D
    ```
