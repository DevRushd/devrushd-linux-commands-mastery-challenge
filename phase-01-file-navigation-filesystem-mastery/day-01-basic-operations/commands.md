## DAY 1 - Where am I? Basic Operations Commands

### The 10 Commands

1. `pwd` : *Print Woring Directory* - This command tells you exactly where you are in your system. 
    Scenario: Just imagine waking up in a strange place or a place you had lost memory about, `pwd` simply remind or tell you the exact location you are. 
    Cloud Use-Case: You can't just run any command in any location on your server, hence the need to always check your location with the `pwd` command.

2. `ls` : *List Content* - This command lists the content of the directory you are currently in.
    Scenario: you trying to take a peek at what is inside an unfamiliar room before entering it. That is exactly what `ls` does.
    Cloud Use-Case: After having found your way into a server by SSH-ing into it, you might need to take a quick glance at what is there before deciding your next move.

3. `ls -l` : *List content in Long format* - The '-l' is an option that tells the terminal to list 
            the content in a long format with permission and ownership relative to the short format of the ordinary 'ls' command.
    Scenario: when you are not satisfied with a peek, you might want to get a handful of additional information without checking the whole stuff in its entirety. 
    Cloud Use-Case: Permissions and ownership are the first thing to check when a file "won't run" or "won't open". 

4. `ls -a` : *List All content including hidden dotfiles* - The '-a' is an option
            that tells the terminal to list all the content, including the hidden files that doesn't appear or show normally.
    Scenario: You noticed some files are missing? No, they are just hidden and you need 'ls -a' to find them.
    Cloud Use-Case: You might be finding it hard to view your AWS CLI credentials. This will need you to get .aws/credentials directory. 'ls' alone won't show it but 'ls -a' will. 

5. `ls -la` : *List All content(hidden files inclusive) in Long format* - Both '-a' and '-l' 
            combines to list all the content, including the hidden files that doesn't appear or show normally in a long format with permission and ownership relative to the short format of the ordinary 'ls' command.
    Scenario: Now, you are getting used to seeing the hidden files and also who owns and can access them. 
    Cloud Use-Case: Cloud engineers mostly use this command to easily check all files with their permissions and ownership.
    
6. `ls -lh` : *List content in long format and human readable sizes* - The '-h' is an option
            that tells the terminal to list the content, in readable data sizes like KB,MB, Gb instead of raw bytes or long numbers.
    Scenario: Instead of a file size like 2147483648, you see 2.0G which is much more easier to read. 
    Cloud Use-Case: On a server, you can spot an oversized log file at a glance and catch disk filling up early with this command.

7. `cd (absolute path)` : *Change Directory to an abolute path* - Takes you directly to the         
                        location of an absolute path(any path starting with /) irrespective of your current location.
    Scenario: Typing the full address of a folder to jump straight there unlike GUI that takes you there after several clicks.
    Cloud Use-Case: From anywhere in the filesystem, cd /etc/systemd/system to check a service unit file without you needing to know where you currently are.

8. `cd ..` : *Change Directory to a step higher in directory level* - Moves up the one directory 
            level.
    Scenario: Go back to the immediate parent folder, just like clicking back in a file explorer.
    Use-Case: Imagine being in three folders deep inside a Terraform module (terraform/modules/vpc/) and you need to go back up to terraform/modules/ to check a dependent module.

9. `cd ~` : *Change Directory to Home* - The tilda "~" sign means "home', so the command takes you  
        back to the home directory regardless of where you are.
    Scenario: You can always find your way home no matter how lost you might get.
    Use-case: After working for long hours in your /var/log/nginx/ directory, you want to get back to your home quickly to grab a script you wrote.

10. `cd -` : *Change Directory to the previous directory* - Moves to the directory you visited last 
            before the one you are currently in.
    Scenario: Go back to wherever you just came from, just like an "undo" for navigation.
    Cloud Use-Case: Very useful when jumping between two different absolute path directories. 
