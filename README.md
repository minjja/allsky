```
apt update
apt install -y docker.io docker-compose git
```

```
docker swarm init
```

```
docker pull nginx:1.23
docker pull ghcr.io/minjja/webdav
docker pull ghcr.io/minjja/allsky-website
```

```
git clone https://github.com/minjja/allsky.git
cd allsky
```

```
docker run --rm httpd htpasswd -nbB $USER $PASSWORD | docker secret create htpasswd -
```

```
docker-compose up -d httpd
docker-compose up certbot
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
