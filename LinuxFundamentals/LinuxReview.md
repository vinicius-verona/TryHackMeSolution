# **Linux Review**
> A linux command/directory review 
---

## **File Operation**
### **chown**
> chown user:group file
- Change the owner and group of a given file
    
    [![image](https://imgur.com/8kYdiUp.jpg)](https://tryhackme.com/room/linux2)

- Let's take as an example the image above. The file `file` belongs to the user `shiba3` and the group `shiba3`, respectively. If we want to change the owner and group to `shiba2` we can use the command `chown shiba2:shiba2 file`.
    
    [![image](https://imgur.com/Q0NwmUk.jpg)](https://tryhackme.com/room/linux2)

- In case you do not wish to specify a group, you can use `chown` to change just the user, such as below.
  
    [![image](https://imgur.com/kFWp8pL.jpg)](https://tryhackme.com/room/linux2)

### **chmod**
> chown permission file
- Change the permission of a given file
- In order to change a file's permission, you must execute the command with a set of 3 numbers:
<br>

| Digit | Means |
| :--:  | :--:  |
| 0 | No permission   |
| 1 | File can be executed   |
| 2 | File can be written to |
| 3 | File can be executed and written to |
| 4 | File can be read |
| 5 | File can be read and executed |
| 6 | file can be read and written to |
| 7 | file can be read, executed and written to|
| | |

<br>

- PS: The digits `1`, `2` and `4` are base values, `3`, `5`, `6` and `7` are a combination of these base values.
- Execution example: `chmod 771 file` gives `file` permission to be executed, read and written to by the user who owns it; permission to be executed, read and written to by the group that owns it and permission to be executed by every other user in the system. 
- How to distinguish permission when we list files with `ls -l`? 
  - In the left side of the list, before each file's owner user, there will be a set of characters such as `-rw-r--r--`. From the `second` hyphen, the first `3` characters control the owner's permission, the next `3`, the group permission and the last `3` controls the permission for every other user in the system. 
  - For example: in the following image, we have `-rw-rw-r-- 1 shiba1 shiba3 0 Feb 20 03:06 file`. Looking at the string `-rw-rw-r--` we know that the user `shiba1` has permission to read and write to `file`, every user from the group `shiba3` has permission to read and write to `file`, and everyone else can read `file`

  [![image](https://imgur.com/kFWp8pL.jpg)](https://tryhackme.com/room/linux2)
---
## **Important Files/Directory/Variables**
- ### **/etc/passwd**
    - Stores user information, such as groups;
    - Usually, it is used to see all users in a system.
- ### **/etc/shadow**
    - Contains all passwords used by the user.
- ### **/tmp**
    - Temporary files, as soon as the system is shutdown, all files are deleted.
- ### **/etc/sudoers**
    - Used to control the sudo permission to all users in the system.
- ### **/home**
    - Similar to the `user` directory in `windows`. It contains all downloads, documents, etc.
- ### **/root**
    - `root` user `/home` directory.
- ### **/usr**
    - where all software is installed.
- ### **/bin and /sbin**
    - Used for system critical files;
    - It contains all programs necessary for `linux` to function properly.
- ### **$PATH**
    - Stores path to all binaries you are permitted to run