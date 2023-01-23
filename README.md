```
apt update
apt install -y docker.io docker-compose git
```

```
docker swarm init
```

```
docker pull nginx
docker pull httpd
docker pull ghcr.io/minjja/webdav
docker pull ghcr.io/minjja/allsky-website
```

```
docker run --rm httpd htpasswd -nbB $USER $PASSWORD | docker secret create htpasswd -
```

```
git clone https://github.com/minjja/allsky.git
cd allsky
```

```
docker-compose up -d httpd
```

```
docker-compose run --rm certbot certonly \
    --agree-tos \
    --cert-name allsky \
    --webroot --webroot-path=/public \
    --register-unsafely-without-email \
    --domains allsky.cloud.cherryservers.net
```

```
docker-compose stop
docker-compose rm -f
```

```
docker stack deploy --compose-file docker-stack.yml allsky
```

```
docker stack rm allsky
```

```
docker secret rm htpasswd
```
