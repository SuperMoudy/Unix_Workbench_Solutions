## 5.9 Writing Programs

### 5.9.5 Exercises

Below this list of exercises you can find examples of how the programs described here should work when used on the command line.

1. Make a script executable.


2. Put that script in a directory that you create and make that directory part of your `PATH`.



3. Write a program called `range` that takes one number as an argument and prints all of the numbers between that number and 0.



4. Write a program called `extremes` which prints the maximum and minimum values of a sequence of numbers.

```bash
$ range 6
```

```
## 0 1 2 3 4 5 6
```

```bash
$ range -3
```

```
## -3 -2 -1 0
```

```bash
$ extremes 8 2 9 4 0 3
```

```
## 0 9
```

---
### Solutions

1. Suppose we have a script named script_name.sh in the home directory:

   - Method 1: Valid for the current shell session
    > Write this in the shell:
    ```bash
    source script_name.sh
    ```

   - Method 2: Valid forever
    > Write this in the ~/.bash_profile or ~/.bashrc
    ```bash
    source script_name.sh
    ```
    > Then, write this in the shell
    ```bash
    source ~/.bash_profile # or ~/.bashrc
    ```
    
---
2. Making the script directory a part of `PATH`:

    ```bash
    mv script_name.sh my_dir/script_name.sh

    export PATH=my_dir:$PATH

    source ~/.bash_profile # or ~/.bashrc
    ```

---
3. `range`

    ```bash
    function range
    {
        local arr=($(eval echo {0..$1}))

        echo ${arr[*]}
    }

    # Test:
    # range $1
    # or source your script and call in the command line
    ```

---
4. `extremes`

    ```bash
    function extremes
    {
        local min=$1
        local max=$1

        for i in $@
        do
            [[ $i -lt $min ]] && let min=$i
            [[ $i -gt $max ]] && let max=$i
        done

        echo $min $max
    }

    # Test:
    # extremes $@
    # or source your script then call in the command line
    ```
    