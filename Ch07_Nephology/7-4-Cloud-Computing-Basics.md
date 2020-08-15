## 7.4 Cloud Computing Basics

### 7.4.5 Exercises


1. Write a bash script that takes a file path as an argument and copies that file to a designated folder on your server.

    ```bash
    $ scp path/to/file username@IP_address:path/to/folder/on/server/
    ```

2. Find a file online that changes periodically, then write a program to download that file every time it changes.

    - Method 1: Manually using console
    ```bash
    $ curl -O The_link_to_the_file
    ```

    - Method 2: Automating this task using `cron` table
    ```bash
    crontab -e
    ```
    > Edit the `cron` table file and adjust your preferred period:
    ```bash
    # Edit this file to introduce tasks to be run by cron.
    #
    # m h  dom mon dow   command
    
    # Runs every hour at the start of the hour
    00 * * * * curl -O The_link_to_the_file
    ```

3. Try creating your own Twitter or GitHub bot with the  [Twitter API](https://dev.twitter.com/rest/public) or the [GitHub API](https://developer.github.com/v3/).

    > Haven't created my own yet, but you can make your own and contribute to this project.

    > To contribute, remove my quotes in this question and replace them with a link to your BOT repo.
