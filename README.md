# Ansible-Playbooks
These are mainly intended for classroom use with Raspberry Pi computers.
## Prerequisites
- Generate public ssh key: `ssh-keygen`
- Copy key to all computers that are to be administrated by Ansible: `ssh-copy-id pi@other-raspi.local`
- Install Ansible __only__ on teacher's computer: `sudo apt update && sudo apt install ansible -y`
## Using the playbooks
- Use a system wide (default: _/etc/ansible/hosts_) or local _hosts_ inventory
- Install a LAMP stack on all hosts in section _labor_:
    ansible-playbook -i hosts lamp.yml --extra-vars="host=labor"
- Shutdown all Raspberries in section _test_ at the end of the class:
    ansible-playbook -i hosts shutdown.yml --extra-vars="host=test"