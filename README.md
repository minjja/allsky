
```
docker pull ghcr.io/minjja/allsky-website:latest
```

```
docker pull k3vmcd/webdav
```

```
docker config rm config.js
docker config create config.js etc/config.js
```

```
docker secret rm htpasswd
docker run --rm k3vmcd/webdav htpasswd -nbB USER PASSWORD | docker secret create htpasswd -
```

```
docker stack rm allsky
```

```
docker stack deploy --compose-file docker-stack.yml allsky
```
