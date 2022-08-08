## How to setup sudo

You wil need to make modifications as the administrative or super, root. At the command line
prompt, type su and press Enter.

```$ su Password:
#```

Now, you need to create a configuration file to enable your user account to user sudo. 
Typically, this file is created in the */etc/sudoers.d/* directory with the mane of the file 
the same as your username.

```# echo "student ALL=(ALL) ALL" > /ect/sudoers.d/student```

Finally, some Linux distributions will complain if you do no also change permission on the file by doing:

```# chmod 440 /etc/sudoers.d/student```
