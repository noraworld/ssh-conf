# ssh-conf
SSH config files.

## Setup
```shell
$ sudo rm /etc/ssh/sshd_config
$ sudo ln -s /path/to/ssh-conf/ssh/sshd_config /etc/ssh
$ sudo rm -r /etc/ssh/sshd_config.d
$ sudo ln -s /path/to/ssh-conf/ssh/sshd_config.d /etc/ssh
```

Generate random port number and add it to `ssh/sshd_config.d/port.conf`.
```shell
# DO NOT EXECUTE BELOW MANY TIMES IN A ROW!
$ echo "Port $(od -An -tu2 -N2 /dev/random | tr -d ' ')" > ssh/sshd_config.d/port.conf
```

If the above command takes too much time, you can use `/dev/urandom` instead of `/dev/random`, but note that the precision of the random number of `/dev/urandom` is poorer than that of `/dev/random`.

cf. https://webbibouroku.com/Blog/Article/linux-rand (Japanese)
