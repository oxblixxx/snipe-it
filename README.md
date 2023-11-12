## About Playbook
This playbook setup an open source project [snipe-it](https://github.com/snipe/snipe-it). The playbook is improved to set each plays as a role.


## How to run
Spin up an ec2 instance, copy ansible user ssh key to server. Set up password for user. Update apachevirtualhost.conf.j2 and file and {fqn} variable in apache roles directory with your public ip address.

Confirm you can ping the instance with `ansible -m ping all`.  

Then run `ansible-playbook -K root-playboks/prod.yml`
