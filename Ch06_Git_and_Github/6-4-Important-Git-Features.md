## 6.4 Important Git Features

### 6.4.4 Exercises

1. Look at the help pages for `git log` and `git diff`.

    ```bash
    $ git help log

    $ git help diff
    ```

2. Add to the `.gitignore` you already started to include a specific file name, then add that file to your repository.

    ```bash
    $ echo "specific_file_name" >> .gitignore
    
    $ touch specific_file_name
    ```

3. Create a file that contains the Git log for this repository. Use `grep` to see which day of the week most of the commits occurred on.

    ```bash
    $ git log > log_file.txt
    ```
    > Next, write this script:

    ```bash
    #!usr/bin/env bash
    # File: log_info.sh

    week_days=(Sat Sun Mon Tue Wed Thu Fri)
    
    max_num=0
    
    max_day="No Day"

    for day in ${week_days[*]}
    do
        num=$(grep $day log_file.txt | wc -l)
        
        if [[ $num -gt $max_num ]]
        then
            let max_num=$num
            
            max_day=$day
        fi
    done

    echo "$max_day: $max_num"
    ```
    > Then, run the script:
    
    ```bash
    $ bash log_info.sh
    ```
