## 5.2 Variables

### 5.2.2 Exercises

1. Write a Bash program where you assign two numbers to different variables, and then the program prints the sum of those variables.

    ```bash
    #!usr/bin/env bash
    # File: ex5-2-q1.sh

    var_x=3
    
    var_y=4
    
    let var_sum=$var_x+$var_y 
    # or var_sum=$(expr $var_x + $var_y)
    
    echo "$var_x + $var_y = $var_sum"
    ```
---
2. Write another Bash program where you assign two strings to different variables, and then the program prints both of those strings. Write a version where the strings are printed on the same line, and a version where the strings are printed on different lines.

    ```bash
    #!usr/bin/env bash
    # File: ex5-2-q2.sh

    str_x="Unix"
    
    str_y="Workbench"
    
    echo "Version 1: $str_x $str_y"
    
    echo -e "Version 2:\n$str_x\n$str_y"
    ```
---
3. Write a Bash program that prints the number of arguments provided to that program multiplied by the first argument provided to the program.

    ```bash
    #!usr/bin/env bash
    # File: ex5-2-q3.sh

    let var_res=$1*$#
    # or var_res=$(expr $1 \* $#)
    
    echo "Result = $var_res"
    ```
