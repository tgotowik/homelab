# Installation
## Network
- vmbr0 VLAN aware

## TODO
```ethtool -K nic0 tso off gso off gro off```
in die /etc/network/interfaces

```
iface nic0 inet manual
        post-up ethtool -K eno1 tso off gso off
```
