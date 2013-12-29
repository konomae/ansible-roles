# ansible-roles

## Environment

- Mac OS X (Host OS)
- Python 2.7
- CentOS 6.4 (Guest OS)


## Install Dependencies

```
pip install -r requirements.txt
```


## Run

```
ansible-playbook -i local site.yml -v -D
```


## Roles

- common
- httpd
- iptables
- mysqld
- ntpd
- ohmyzsh
- php
- pyenv
- redis
- sshd
- user
- vhost
- xdebug
