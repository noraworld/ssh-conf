# ssh-conf
SSH config files.

## Setup
```shell
cd ssh-conf
sudo rm    /etc/ssh/sshd_config
sudo ln -s $PWD/ssh/sshd_config /etc/ssh
sudo rm -r /etc/ssh/sshd_config.d
sudo ln -s $PWD/ssh/sshd_config.d /etc/ssh
sudo rm    /etc/ssh/ssh_config
sudo ln -s $PWD/ssh/ssh_config /etc/ssh
```

Generate random port number and add it to `ssh/sshd_config.d/port.conf`.
```shell
# DO NOT EXECUTE BELOW MANY TIMES IN A ROW!
echo "Port $(od -An -tu2 -N2 /dev/random | tr -d ' ')" | tee -a $PWD/ssh/sshd_config.d/port.conf
```

If the above command takes too much time, you can use `/dev/urandom` instead of `/dev/random`, but note that the precision of the random number of `/dev/urandom` is poorer than that of `/dev/random`.

cf. https://webbibouroku.com/Blog/Article/linux-rand (Japanese)
