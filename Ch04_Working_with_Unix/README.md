## Chapter 4: Working with Unix

### 4.1.2 Exercises

1. Use `man` to look up the flag for human-readable output from `ls`.

    ```bash
    man ls
    ```
    And in the man page search:
    ```
    /human-readable
    ```

2. Get help with `man` by typing `man man` into the console.

    ```bash
    man man
    ```

3. Wouldn't it be nice if there was a calendar command? Use `apropos` to look for such a command, then use `man` to read about how that command works.

    ```bash
    apropos calendar

    man calendar
    ```

---
### 4.2.2 Exercises

1. Before I organized the photos by year, what command would have listed all of the photos of type `.png`?

    ```bash
    ls *.png
    ```

2. Before I organized the photos by year, what command would have deleted all of my hiking photos?

    ```bash
    rm *hiking*
    ```

3. What series of commands would you use in order to put my figures for a data science course and the pictures I took in the lab into their own folders?

    ```bash
    mv *datasci* data_science_course/

    mv *lab* lab/
    ```

---
### 4.3.7 Exercises

1. Search `states.txt` and `canada.txt` for lines that contain the word "New".

    ```bash
    grep "New" states.txt canada.txt
    ```

2. Make five text files containing the names of states that don't contain one of each of the five vowels.

    ```bash
    egrep -v "a" states.txt >> states_no_a.txt

    egrep -v "e" states.txt >> states_no_e.txt

    egrep -v "i" states.txt >> states_no_i.txt

    egrep -v "o" states.txt >> states_no_o.txt

    egrep -v "u" states.txt >> states_no_u.txt
    ```

3. Download the GitHub repository for this book and find out how many `.html` files it contains

    ```bash
    git clone https://github.com/seankross/the-unix-workbench

    cd the-unix-workbench

    find . -name "*.html" | wc -l
    ```

---
### 4.6.2 Exercises

1. Use pipes to figure out how many US states contain the word "New."

    ```bash
    grep "New\." states.txt | wc -l
    ```

2. Examine your `~/.bash_history` to try to figure out how many unique commands you've ever used. (You may need to look up how to use the `uniq` and `sort` commands).

    ```bash
    cat ~/.bash_history | sort | uniq | wc -l
    ```
