# Installation
Make sure your public key is installed on ~/.ssh/authorized_keys

```
ansible-playbook -i inventory/inventory.ini playbooks/site.yml -l all -t onboard

ansible-playbook -i inventory/inventory.ini playbooks/site.yml -l nextcloud -t onboard
```

### unattented-upgrades
- check with ```unattended-upgrades --dry-run --debug```

### mail
- check if msmtp working: ```printf "To: example@gmail.com\nSubject: Test\n\nTest" | msmtp -a strato example@gmail.com```
- check if mail working: ```echo "Test" | mail -s "Unattended-Upgrades Test" example@gmail.com```