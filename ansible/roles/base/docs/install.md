# Installation

Installs:
    - updates
    - hostname
    - drives

```ansible-playbook -i inventory/inventory.ini playbooks/1_base.yml -l main```

### unattented-upgrades
- check with ```unattended-upgrades --dry-run --debug```

### mail
- check if msmtp working: ```echo "Test" | msmtp -a gmail example@gmail.com```
- check if mail working: ```echo "Test" | mail -s "Unattended-Upgrades Test" example@gmail.com```