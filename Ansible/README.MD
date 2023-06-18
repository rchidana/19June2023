### Configuring Cisco Routers to connect from our Lab Ubuntu system


Append the following to /etc/ansible/hosts file (need sudo rights to do it) <br>

```
[routers]
sandbox-iosxe-latest-1.cisco.com

[routers:vars]
ansible_user=developer
ansible_password=C1sco12345
ansible_connection=network_cli
ansible_network_os=ios
ansible_port=22
```

Additionally, in the /etc/ansible/ansible.cfg, add or uncomment the following configurations<br>

```
host_key_checking=False
```

Fire your first ansible adhoc command as follows <br>

```
ansible routers -m ping -vvvv
ansible routers -m ios_command -a "commands='show version'"
ansible routers -m ios_command -a "commands='show clock'"
ansible routers -m ios_command -a "commands='show interfaces'"
```
