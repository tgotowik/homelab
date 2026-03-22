# Installation
```ansible-playbook -i inventory/inventory.ini playbooks/3_docker.yml -l main```

self signed certificate for local services:
```openssl req -x509 -nodes -days 3650 -newkey rsa:4096 -keyout /etc/ssl/private/tgotowik.key -out /etc/ssl/certs/tgotowik.crt -config /root/tgotowik-ssl.conf -extensions v3_req```