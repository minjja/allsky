
```sh
docker config rm config.js
docker config create config.js etc/config.js
```

```sh
docker pull ghcr.io/minjja/allsky-website:latest
```

```sh
docker stack rm allsky
```

```sh
docker stack deploy --compose-file docker-stack.yml allsky
```
