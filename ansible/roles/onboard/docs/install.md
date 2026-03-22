# Installation
Make sure sudo is installed and ansible user is in /etc/sudoers for first start

Installs and configure ssh and sudo
```
ansible-playbook -i inventory/inventory.ini playbooks/site.yml \
  -l vaultwarden \
  -t onboard \
  --become-method=su \
  --become-user=root \
  --ask-become-pass
```

after run, delete line from /etc/sudoers file