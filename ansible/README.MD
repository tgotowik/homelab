# Setup
### Setup ansible-vault
- Create file with your secrets
- encrypt with ```ansible-vault encrypt inventory/group_vars/main/vault```
- setup ansible.cfg: vault_password_file
- run playbooks: ```ansible-playbook --ask-vault-pass -i inventory/inventory.ini playbooks/1_base.yml -l main" if no password file exists