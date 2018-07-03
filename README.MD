Ansible Configuration Playbooks
===============================

Ansible provides SSH-based configuration management for remote hosts.


## Bootstrapping

After bringing up a new host, perform the following steps to prepare the node
for ansible management:

```shell
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install python
```

## Update inventory.ini
Change line 4 of `inventory.ini` to use your Pi's IP address:
```
[freedomnet]
10.0.1.29 <-- YOUR IP HERE
```

## Run Playbook
On your host machine (NOT the pi) run:
```
$ ansible-playbook site.yml -i inventory.ini
```

Note: if you want to use password authentication use the `-k` flag:
```
$ ansible-playbook site.yml -k -i inventory.ini
```

Finally, reboot the Pi. When it comes back up you should see a new Wifi access point: FreedomNet. Connect to it and experience the freedom!

## IMPORTANT NOTE
After running the above playbook the pi won't connect to Wifi APs anymore. If you enabled SSH you can join FreedomNet and log in using that. If not, you will need to plug into a monitor and keyboard.