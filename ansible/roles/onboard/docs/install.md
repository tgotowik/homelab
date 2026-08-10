# Installation

# VMs
when no ssh key is installed
sudo must be installed
```
ansible-playbook -i inventory/inventory.ini playbooks/bootstrap.yml -l vaultwarden --ask-pass --ask-become-pass
```

### unattented-upgrades
- check with ```unattended-upgrades --dry-run --debug```

### mail
- check if msmtp working: ```printf "To: example@gmail.com\nSubject: Test\n\nTest" | msmtp -a strato example@gmail.com```
- check if mail working: ```echo "Test" | mail -s "Unattended-Upgrades Test" example@gmail.com```