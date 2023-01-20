```
docker pull ghcr.io/minjja/allsky-website:latest
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
