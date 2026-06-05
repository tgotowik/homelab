# Installation
Make sure sudo is installed and ansible user is in /etc/sudoers for first start, when physical clean installed os.

```
ansible-playbook -i inventory/inventory.ini playbooks/site.yml \
  -l vaultwarden \
  -t onboard \
  --become-method=su \
  --become-user=root \
  --ask-become-pass

on container or vms:
ansible-playbook -i inventory/inventory.ini playbooks/site.yml -l all -t onboard
```

after run, delete line from /etc/sudoers file

```ansible-playbook -i inventory/inventory.ini playbooks/site.yml -t base -l vaultwarden```

### unattented-upgrades
- check with ```unattended-upgrades --dry-run --debug```

### mail
- check if msmtp working: ```printf "To: example@gmail.com\nSubject: Test\n\nTest" | msmtp -a strato example@gmail.com```
- check if mail working: ```echo "Test" | mail -s "Unattended-Upgrades Test" example@gmail.com```