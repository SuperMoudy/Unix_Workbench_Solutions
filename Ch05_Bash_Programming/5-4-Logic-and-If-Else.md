## 5.4 Logic and If/Else

### 5.4.5 Exercises

1. Write a Bash script that takes a string as an argument and prints "how proper" if the string starts with a capital letter.

    ```bash
    #!usr/bin/env bash
    # File: ex5-4-q1.sh

    [[ $1 =~ ^[A-Z] ]] && echo "how proper"
    ```
---
2. Write a Bash script that takes one argument and prints "even" if the first argument is an even number or "odd" if the first argument is an odd number.

    ```bash
    #!usr/bin/env bash
    # File: ex5-4-q2.sh

    [[ $1%2 -eq 0 ]] && echo "even" || echo "odd"
    ```
---
3. Write a Bash script that takes two arguments. If both arguments are numbers, print their sum, otherwise just print both arguments.

    ```bash
    #!usr/bin/env bash
    # File: ex5-4-q3.sh

    if [[ $1 =~ ^[0-9]+$ ]] && [[ $2 =~ ^[0-9]+$ ]]
    then
        let sum=$1+$2
        echo $sum
    else
        echo "$1 $2"
    fi
    ```
---
4. Write a Bash script that prints "Thank Moses it's Friday" if today is Friday.
(Hint: take a look at the `date` program).

    ```bash
    #!usr/bin/env bash
    # File: ex5-4-q4.sh

    [[ $(date +%A) = "Friday" ]] && echo "Thank Moses it's Friday"
    ```
