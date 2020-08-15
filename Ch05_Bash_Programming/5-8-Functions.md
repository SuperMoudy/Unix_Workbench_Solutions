## 5.8 Functions

### 5.8.4 Exercises

Below this list of exercises you can find examples of how these programs should work when used on the command line.

1. Write a function called `plier` which multiplies together a sequence of numbers.



2. Write a function called `isiteven` that prints `1` if a number is even or `0` a number is not even.



3. Write a function called `nevens` which prints the number of even numbers when provided with a sequence of numbers. Use `isiteven` when writing this function.



4. Write a function called `howodd` which prints the percentage of odd numbers in a sequence of numbers. Use `nevens` when writing this function.



5. Write a function called `fib` which prints the number of [fibonacci](https://en.wikipedia.org/wiki/Fibonacci_number) numbers specified.

```bash
$ plier 7 2 3
```

```
## 42
```

```bash
$ isiteven 42
```

```
## 1
```

```bash
$ nevens 42 6 7 9 33
```

```
## 2
```

```bash
$ howodd 42 6 7 9 33
```

```
## .60
```

```bash
$ fib 4
```

```
## 0 1 1 2
```

```bash
$ fib 10
```

```
## 0 1 1 2 3 5 8 13 21 34
```
---

### Solutions

1. `plier`

    ```bash
    #!usr/bin/env bash
    # File: ex5-8-q1.sh

    function plier
    {
        local res=1

        for num in $@
        do
            let res=$res\*$num
        done

        echo $res
    }

    # Test:
    # Method 1:
    # Uncomment the next line here and run the script using bash
    # plier $@

    # Method 2:
    # Write the next line in the command line then call 
    # the function name with arbitrary arguments
    # source ex5-8-q1.sh
    ```

2. `isiteven`

    ```bash
    #!usr/bin/env bash
    # File: ex5-8-q2.sh

    function isiteven
    {
        [[ $1%2 -eq 0 ]] && echo 1 || echo 0
    }

    # Test:
    # Method 1:
    # Uncomment the next line here and run the script using bash
    # isiteven $1

    # Method 2:
    # Write the next line in the command line then call 
    # the function name with arbitrary arguments
    # source ex5-8-q2.sh
    ```

3. `nevens`

    ```bash
    #!usr/bin/env bash
    # File: ex5-8-q3.sh

    function neven
    {
        local sum=0

        for num in $@
        do
            let sum=$sum+$(isiteven $num)
        done

        echo $sum
    }

    # Test:
    # Method 1:
    # Uncomment the next line here and run the script using bash
    # neven $@

    # Method 2:
    # Write the next line in the command line then call 
    # the function name with arbitrary arguments
    # source ex5-8-q3.sh
    ```

4. `howodd`

    ```bash
    #!usr/bin/env bash
    # File: ex5-8-q4.sh

    function howodd
    {
        howeven=$(neven $@)

        printf "%.2f\n" $(echo 1.0 - $howeven / $# | bc -l)
    }

    # Test:
    # Method 1:
    # Uncomment the next line here and run the script using bash
    # howodd $@

    # Method 2:
    # Write the next line in the command line then call 
    # the function name with arbitrary arguments
    # source ex5-8-q4.sh
    ```

5. `fib`

    ```bash
    #!usr/bin/env bash
    # File: ex5-8-q5.sh

    function fib
    {
        if [[ $1 -eq 1 ]]
        then
            echo 0
        elif [[ $1 -eq 2 ]]
        then
            echo 0 1
        else
            # Starting elements of the series
            local arr=(0 1)

            # Number of elements to be added to the series
            local end=$(expr $1 - 2)

            # Local variable of the current element to be added
            local element=0

            # Iterate 'end' times
            for i in $(eval echo {1..$end})
            do
                # element = last + 2nd_last
                let element=${arr[-1]}+${arr[-2]}
                
                # element becomes the new last
                arr+=($element)
            done

            echo ${arr[*]}
        fi      
    }

    # Test:
    # Method 1:
    # Uncomment the next line here and run the script using bash
    # fib $1

    # Method 2:
    # Write the next line in the command line then call 
    # the function name with arbitrary arguments
    # source ex5-8-q5.sh
    ```
