# Installation
- run ```ansible-playbook -i inventory/inventory.ini playbooks/2_webserver.yml -l main```
- check ddclient with  ```ddclient -daemon=0 -debug -verbose -noquiet```
- get certificates ```certbot --apache -d tgotowik.de -d www.tgotowik.de -d nas.tgotowik.de -d bw.tgotowik.de -d immich.tgotowik.de```