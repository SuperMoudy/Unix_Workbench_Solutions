## 5.5 Arrays

### 5.5.2 Exercises

1. Write a bash script where you define an array inside of the script, and the first argument for the script indicates the index of the array element that is printed to the console when the script is run.

    ```bash
    #!usr/bin/env bash
    # File: ex5-5-q1.sh

    arr=(A B C D E F G)

    echo ${arr[$1]}
    ```

2. Write a bash script where you define two arrays inside of the script, and the sum of the lengths of the arrays are printed to the console when the script is
run.

    ```bash
    #!usr/bin/env bash
    # File: ex5-5-q2.sh
    
    arr1=(fire earth water wind darkness light)
    
    arr2=(red blue yellow green brown black white grey)

    let len_sum=${#arr1[*]}+${#arr2[*]}
    
    echo "$len_sum"
    ```
