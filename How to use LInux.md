# How to Use Linux?

## File Manupulation

- Open a new terminal window: `Ctrl + Alt + T`

- List the contents of current directory: `ls`

- Create a new directory: `mkdir`

- Create a new file: `touch`

- Use **Nano** to create a file .txt: 

    Write in the terminal `nano filename.txt`, then a nano window will come out

    Type whatever the content in this file

    Save it by `Ctrl + O`

    Exit it by `Ctrl + X`
- Copy FIle: `cp filename-in-current-directory destination`

- Rename file: `mv current-filename changed-filename`

- Delete a single file: `rm filename`

    Delete an empty directory: `rm -d dirname` 

    Delete a non-empty directory: `rm -rf dirname`

## Package Management#

## System

- Check version of system: `cat /etc/os-release`

- Determine the serial number of a computer： `sudo dmidecode -t system | grep Serial`

- Shutdown `shutdown now`

- Reboot `shutdown -r now`