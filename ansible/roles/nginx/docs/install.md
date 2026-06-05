# Installation
- run ```ansible-playbook -i inventory/inventory.ini playbooks/2_webserver.yml -l main```
- check ddclient with  ```ddclient -daemon=0 -debug -verbose -noquiet```
- get certificates ```certbot --apache -d tgotowik.de -d www.tgotowik.de -d nas.tgotowik.de -d bw.tgotowik.de -d immich.tgotowik.de```
- hostcert ```openssl req -x509 -nodes -days 3650 -newkey rsa:4096 -keyout /etc/ssl/private/host.key -out /etc/ssl/certs/host.crt -config /root/hostcert-ssl.conf -extensions v3_req```