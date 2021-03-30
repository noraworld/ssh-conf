# ssh-conf
SSH config files.

## Setup
```shell
$ sudo rm /etc/ssh/sshd_config
$ sudo ln -s /path/to/ssh-conf/ssh/sshd_config /etc/ssh
$ sudo rm -r /etc/ssh/sshd_config.d
$ sudo ln -s /path/to/ssh-conf/ssh/sshd_config.d /etc/ssh
```
