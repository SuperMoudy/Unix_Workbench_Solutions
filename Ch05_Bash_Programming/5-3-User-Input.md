## 5.3 User Input

### 5.3.2 Exercises


1. Write a script that asks the user for an adjective, a noun, and a verb, and then use those words in a sentence (like [Mad Libs](https://en.wikipedia.org/wiki/Mad_Libs)).

    ```bash
    #!usr/bin/env bash
    # File: ex5-3-q1.sh

    echo -n "Enter an adjective: "
    read adj

    echo -n "Enter a noun: "
    read noun

    echo -n "Enter a verb: "
    read verb

    echo "Sentence: $noun $verb $adj."

    ```
