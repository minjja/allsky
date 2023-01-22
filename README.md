```
docker pull ghcr.io/minjja/allsky-website
```

```
docker pull ghcr.io/minjja/webdav
```

```
docker secret rm htpasswd
docker run --rm htppd htpasswd -nbB USER PASSWORD | docker secret create htpasswd -
```

```
docker stack rm allsky
```

```
docker stack deploy --compose-file docker-stack.yml allsky
```

```
docker run --rm -ti \
    --mount source=allsky_html,target=/public \
    certbot/certbot \
    certonly \
    --webroot --webroot-path=/public \
    --register-unsafely-without-email \
    --agree-tos \
    -d allsky2.cloud.cherryservers.net \
    -v
```
