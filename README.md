```
docker pull ghcr.io/minjja/allsky-website:latest
```

```
docker config rm config.js
docker config create config.js etc/config.js
```

```
docker config rm virtualsky.json
docker config create virtualsky.json etc/virtualsky.json
```

```
docker secret rm htpasswd
docker run --rm ghcr.io/minjja/allsky-website htpasswd -nbB USER PASSWORD | docker secret create htpasswd -
```

```
docker stack rm allsky
```

```
docker stack deploy --compose-file docker-stack.yml allsky
```
