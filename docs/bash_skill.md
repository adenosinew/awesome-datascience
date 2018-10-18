# Bash skill

[toc]


## Must known Bash commands
ls

mv

cp

cd

touch

rm

wc

grep


## Efficient shortcuts

### Move cursor

- ```ctrl + a``` : move to the beginning of the input

- ```ctrl + e``` : move to the end of the input

### command substitution

```^before^after^``` means using **after** to replace **before**. 

For instance:

```shell
# this command has error
eho "hello world"

# fix the command
^e^ec^
# eho -> echo
```

### create alias

```shell
alias login_my_host="ssh -i id_rsa ubuntu@192.168.0.1"
```

when the user type ```login_my_host```, it will excute the string and then ssh to the host.

write the alias to ~/.bashrc file if you want to reuse the alias.

use ```unalias``` to remove the alias


### reuse commands
use **!** to reuse the command
```shell
# reuse the last command
!!

# reuse the last command started with string "****ec"
!ec

# resure the No.2000 command in the history
!2000
```

### dynamic update some files
```shell
tail -f somefile
```

Black magic (get stdout for some process)

```shell
# use top to get the PID for some processes
top

[output]
# for instance, my terminal has the PID 1340
1340 kexing    20      846752  46600  34144 S   3.3   0.3   0:12.60 /usr/bin/deepin-terminal                                     

# dynamic update the stdout for PID 1340
tail -f /proc/1340/fd/1
```


