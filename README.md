# passbolt Community Edition in docker compose with MTA and ssl

Firstly install certbot and obtain an certificate for your domain

```
git clone https://github.com/akshakirov/passbolt.git

cd passbolt

export MYSQL_PASSWORD=DesiredMySQLpasswordHere
export PASSBOLT_DOMAIN=passbolt.test.com

certbot certonly -d $PASSBOLT_DOMAIN --agree-tos

docker compose -f docker-compose-ce.yaml up -d
```

root mysql password can be obtained by:

``` docker logs passbolt-db-1  2>/dev/null | grep "GENERATED ROOT PASSWORD" ```
