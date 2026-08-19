# Installation
- run ```ansible-playbook -i inventory/inventory.ini playbooks/site.yml -l nginx -t nginx```
- check ddclient with  ```ddclient -daemon=0 -debug -verbose -noquiet```
- get certificates ```certbot certonly --dry-run --nginx --cert-name tgotowik.de-0001 -d tgotowik.de -d www.tgotowik.de -d nas.tgotowik.de -d bw.tgotowik.de -d photos.tgotowik.de -d jf.tgotowik.de```
- hostcert ```openssl req -x509 -nodes -days 3650 -newkey rsa:4096 -keyout /etc/ssl/private/host.key -out /etc/ssl/certs/host.crt -config /root/hostcert-ssl.conf -extensions v3_req
- curl -L https://ssl-config.mozilla.org/ffdhe2048.txt -o /etc/dhparam
```

## pve fw
```
IN ACCEPT -p tcp -dport 443 -log nolog # https
IN ACCEPT -source 192.168.178.26/32 -p tcp -dport 22 -log nolog # Allow my pc
OUT REJECT -p tcp -dport 22 -log nolog # Block ssh
```