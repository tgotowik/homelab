# Installation
## pve fw
```
IN ACCEPT -source 192.168.178.26/32 -p tcp -dport 22 -log nolog # Allow my pc
OUT REJECT -p tcp -dport 22 -log nolog # Block ssh
IN ACCEPT -p tcp -dport 2283 -log nolog # nginx
```