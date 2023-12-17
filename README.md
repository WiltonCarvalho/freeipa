# freeipa
```
sudo cp /etc/docker/daemon.json /etc/docker/daemon.json_bkp
echo '{ "userns-remap": "default" }' | sudo tee /etc/docker/daemon.json

systemctl restart docker
```
```
docker-compose up -d
docker-compose logs -f
```
```
(
  export TLS_REQCERT=never
  ldapsearch -x -LLL -H ldaps://localhost \
    -D "uid=admin,cn=users,cn=accounts,dc=example,dc=local" \
    -wpassw0rd -b "dc=example,dc=local" \
    "(&(objectclass=person)(uid=admin))"
)
```
```
echo "127.0.0.1 ipa.example.local" | sudo tee -a /etc/hosts
firefox ipa.example.local
```