## ansible-homeassistant

* First of all: work in progress
* Second, you config should be in roles/homeassistant/files/config


in a seperate repo you will need to create your config.
To make the hassbian part work add the following file in /etc/ansible/facts.d/hassbian
```
{
  "hassbian": true
}
```

## Inventory file
For ansible you need an inventory file I use something simmilar to this:
```
pi ansible_host=hostip ansible_user=pi  ansible_ssh_common_args="-o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null" ansible_password=guess
```

## How to run it
This is what I use
```
ansible-playbook -i inventory --limit pi  config.yml -k
```

## Centos on Raspberry PI
short answer no

Long answer: as you need Python3.x, you need software collections and they are not available on Centos 7 for armhf


## Todo
* Add a call to the HA websocket when needed, saves some time
* Libcec and other optionals with parameters instead of always


## Pull requests
YES!