## Hardening playbooks

*This playbook has only been designed for Ubuntu 16.04+. You will have to modify the calls for the Ansible systemd modules to init.d for any Ubuntu release older than 16.04.* 


### How to use on local machine:


1. Install ansible:

```
sudo apt-get update
sudo apt-get install software-properties-common -y
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt-get install ansible -y
```

Also, install Python if it isn't installed:

```
sudo apt-get update
sudo apt-get install python -y
```


2. Download this repository and `cd` into the hardening directory:

```
git clone https://github.com/heywoodlh/ubuntu-playbooks
cd ubuntu-playbooks/security/hardening
```


3. Edit the variables in `inventory` file with desired configuration:

```
nano inventory
```


4. It is recommended to edit the banner that will be displayed on the machine:

```
nano roles/ssh/files/motd
```


5. Once inventory and your banner are configured, run the playbook using the inventory file:

```
ansible-playbook -i inventory harden.yml
```


If you don't plan to use Ansible at all afterward, feel free to uninstall Ansible:

```
sudo apt-get remove ansible -y
sudo apt-get autoremove
```
