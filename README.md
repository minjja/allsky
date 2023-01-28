```
apt update
apt install -y docker.io git
```

```
docker swarm init
```

```
docker pull nginx
docker pull httpd
docker pull certbot/certbot
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
docker run --rm -v ${PWD}/ssl/live/allsky:/ssl httpd \
    openssl req -x509 -newkey rsa:2048 -days 1000 -nodes \
    -keyout /ssl/privkey.pem \
    -out /ssl/cert.pem \
    -subj "/CN=localhost:-selfsigned"
```

```
docker stack deploy --compose-file docker-stack.yml allsky
```

```
docker run --rm -v allsky_html:/public -v ${PWD}/ssl:/etc/letsencrypt certbot/certbot certonly \
    --agree-tos \
    --cert-name allsky \
    --webroot --webroot-path=/public \
    --register-unsafely-without-email \
    --domains allsky.cloud.cherryservers.net
```

```
docker stack rm allsky
```

```
docker secret rm htpasswd
```
