# Installation
```
ansible-playbook -i inventory/inventory.ini playbooks/site.yml -l nextcloud -t nextcloud
```
## Container Setup
- Debian 13
- Options:
    - fuse=1 
- Resources:
    - mount tank to /nextcloud
    - Passthrough