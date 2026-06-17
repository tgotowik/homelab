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

# Nextcloud AIO
Edit config.php
```
docker run -it --rm --volume nextcloud_aio_mastercontainer:/mnt/docker-aio-config:rw alpine sh -c "apk add --no-cache nano && nano /mnt/docker-aio-config/data/configuration.json"
```

## pve fw
```
IN ACCEPT -source 192.168.178.26/32 -p tcp -dport 22 -log nolog # Allow my pc
OUT REJECT -p tcp -dport 22 -log nolog # Block ssh
IN ACCEPT -p tcp -dport 11000 -log nolog # nginx
```